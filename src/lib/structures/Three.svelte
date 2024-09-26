<script>
  import { onMount } from "svelte";
  import * as THREE from "three";

  import backgoundImage from "$lib/assets/40.jpg";

  let container;
  let camera, scene, renderer, planeMesh;
  let animationFrameId;
  let cachedCanvas;

  let currentState = {
    mousePosition: { x: 0, y: 0 },
    waveIntensity: 0.01,
    scrollY: 0,
    scrollIntensity: 0.2, // New property
  };
  let targetState = {
    mousePosition: { x: 0, y: 0 },
    waveIntensity: 0.005,
    scrollY: 0,
    scrollIntensity: 0.2, // New property
  };

  const ANIMATION_CONFIG = {
    transitionSpeed: 0.03,
    baseIntensity: 0.03,
    hoverIntensity: 0.009,
  };

  // Shaders

  const vertexShader = `
    varying vec2 vUv;
    void main() {
        vUv = uv;
        gl_Position = projectionMatrix * modelViewMatrix * vec4(position, 1.0);
    }
`;

  const fragmentShader = `uniform float u_time;
    uniform vec2 u_mouse;
    uniform float u_intensity;
    uniform float u_scrollY; // New uniform for scroll position
    uniform sampler2D u_texture;
    varying vec2 vUv;

    void main() {
        vec2 uv = vUv;
        float scrollEffect = u_scrollY * 0.001; // Simple scroll effect, adjust as needed
        float wave1 = sin(uv.x * 1.0 + u_time * 0.5 + u_mouse.x * 5.0 + scrollEffect) * u_intensity;
        float wave2 = sin(uv.y * 12.0 + u_time * 0.8 + u_mouse.y * 4.0 + scrollEffect) * u_intensity;
        float wave3 = cos(uv.x * 8.0 + u_time * 0.5 + u_mouse.x * 3.0 + scrollEffect) * u_intensity;
        float wave4 = cos(uv.y * 9.0 + u_time * 0.7 + u_mouse.y * 3.5 + scrollEffect) * u_intensity;

        uv.y += wave1 + wave2;
        uv.x += wave3 + wave4;
        
        gl_FragColor = texture2D(u_texture, uv);
    }`;

  onMount(() => {
    window.scrollTo(0, 0); // Reset scroll position to the top

    cachedCanvas = document.createElement("canvas");

    window.addEventListener("scroll", handleScroll);

    const imageElement = document.getElementById("myImage");
    init(new THREE.TextureLoader().load(imageElement.src));
    animate();

    return () => {
      window.removeEventListener("resize", onWindowResize);
      window.removeEventListener("scroll", handleScroll);

      cancelAnimationFrame(animationFrameId);
    };
  });

  function init(texture) {
    // Camera setup
    // Initial camera setup
    const aspectRatio = window.innerWidth / window.innerHeight;

    camera = new THREE.PerspectiveCamera(
      window.innerWidth < 768 ? 90 : 100,
      aspectRatio,
      0.1,
      1000
    );

    camera.position.z = 1;

    // Scene creation
    scene = new THREE.Scene();

    // Uniforms
    const shaderUniforms = {
      u_time: { type: "f", value: 1.0 },
      u_mouse: { type: "v2", value: new THREE.Vector2() },
      u_intensity: { type: "f", value: currentState.waveIntensity },
      u_texture: { type: "t", value: texture },
    };

    // Calculate the plane size based on the camera's frustum
    const frustumHeight =
      2 * Math.tan((camera.fov * Math.PI) / 180 / 2) * camera.position.z;
    const frustumWidth = frustumHeight * camera.aspect;

    planeMesh = new THREE.Mesh(
      new THREE.PlaneGeometry(frustumWidth, frustumHeight),
      new THREE.ShaderMaterial({
        uniforms: shaderUniforms,
        vertexShader,
        fragmentShader,
      })
    );

    // Add mesh to the scene
    scene.add(planeMesh);

    // Renderer
    renderer = new THREE.WebGLRenderer({ antialias: true });
    renderer.setSize(window.innerWidth, window.innerHeight);
    container.appendChild(renderer.domElement);

    // Event listeners for mouse interaction
    container.addEventListener("mousemove", handleMouseMove, false);
    container.addEventListener("mouseover", handleMouseOver, false);
    container.addEventListener("mouseout", handleMouseOut, false);

    // Handle window resize
    // window.addEventListener("resize", onWindowResize, false);
  }

  function animate() {
    animationFrameId = requestAnimationFrame(animate);

    // Update shader uniforms based on mouse movement and intensity
    updateShaderUniforms();

    renderer.render(scene, camera);
  }

  function updateShaderUniforms() {
    currentState.mousePosition.x = updateValue(
      targetState.mousePosition.x,
      currentState.mousePosition.x,
      ANIMATION_CONFIG.transitionSpeed
    );

    currentState.mousePosition.y = updateValue(
      targetState.mousePosition.y,
      currentState.mousePosition.y,
      ANIMATION_CONFIG.transitionSpeed
    );

    currentState.waveIntensity = updateValue(
      targetState.waveIntensity,
      currentState.waveIntensity,
      ANIMATION_CONFIG.transitionSpeed
    );

    const uniforms = planeMesh.material.uniforms;
    uniforms.u_intensity.value = currentState.waveIntensity;
    uniforms.u_time.value += 0.005;
    uniforms.u_mouse.value.set(
      currentState.mousePosition.x,
      currentState.mousePosition.y
    );
  }

  function handleScroll() {
    const scrollPercentage =
      window.scrollY / (document.body.offsetHeight - window.innerHeight);
    targetState.scrollIntensity = scrollPercentage; // Simple linear mapping, adjust as needed
  }

  function handleMouseMove(event) {
    const rect = container.getBoundingClientRect();
    targetState.mousePosition.x =
      ((event.clientX - rect.left) / rect.width) * 2 - 1;
    targetState.mousePosition.y =
      -((event.clientY - rect.top) / rect.height) * 2 + 1;
  }

  function handleMouseOver() {
    targetState.waveIntensity = ANIMATION_CONFIG.hoverIntensity;
  }

  function handleMouseOut() {
    targetState.waveIntensity = ANIMATION_CONFIG.baseIntensity;
    targetState.mousePosition = { x: 0, y: 0 };
  }

  function updateValue(target, current, transitionSpeed) {
    return current + (target - current) * transitionSpeed;
  }

  function onWindowResize() {
    const aspectRatio = 16 / 9;
    camera.aspect = aspectRatio;
    camera.updateProjectionMatrix();
    camera.aspect = aspectRatio;
  }
</script>

<div bind:this={container}></div>

<div class="animated__background" id="imageContainer">
  <img id="myImage" src={backgoundImage} alt="" />
</div>

<style>
  .animated__background {
    position: relative;
    top: 0;
    inset: 0;
    width: 100%;
    height: 100svh;
    z-index: -1;
  }

  :is(canvas) {
    display: block;
    transition: 1s transform;
    width: 100%;
    height: 100svh;
    overflow: visible;
  }

  #imageContainer {
    position: relative;
    width: 100%;
    height: 100svh;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10px;
    max-width: 100%;
    transition: all ease 0.5s;
    display: none;
  }

  #myImage {
    object-fit: cover; /* Covers the entire area of the container, may crop the image */
    display: none;
    mix-blend-mode: color-burn;
  }

  #imageContainer > * {
    position: absolute;
    inset: 0;
    height: 100svh !important;
    width: 100% !important;
    object-fit: cover !important;
  }

  @media (max-width: 768px) {
    .animated__background {
    }
  }
</style>
