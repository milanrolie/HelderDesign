<script>
  import { gsap } from "gsap";
  import { onMount } from "svelte";
  import SiteHeader from "$lib/structures/SiteHeader.svelte";
  import logo from "$lib/assets/logo__reveal.png";

  let threeLoaded = false;

  function handleThreeLoaded() {
    threeLoaded = true;
  }

  onMount(() => {
    const tl = gsap.timeline();

    tl.to(".logo__reveal", {
      duration: 1,
      opacity: 1,
      ease: "power1.in",
    });

    gsap.to(".logo__reveal", {
      duration: 1.5,
      delay: 1.2,
      ease: "power1.out",
    });

    gsap.to(".logo__reveal", {
      duration: 1.5,
      delay: 2,
      ease: "power1.out",
      filter: "blur(30px)", // Add blur effect here
      scale: 4,
    });

    gsap.to(".logo__reveal", {
      duration: 1,
      delay: 3,
      opacity: 0,
      ease: "power1.out",
    });

    gsap.to(".gsap-reveal", {
      delay: 2,
      duration: 1,
      ease: "power1.out",
      scale: 4,
    });

    gsap.to(".gsap-reveal", {
      delay: 3,
      duration: 2,
      ease: "power1.out",
      opacity: 0,
    });
  });
</script>

<SiteHeader on:threeLoaded={handleThreeLoaded} />

<section class="gsap-reveal">
  <div class="logo-wrapper">
    <img class="logo__reveal" src={logo} alt="" />
  </div>
</section>

<style>
  section {
    position: fixed;
    height: 100svh;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    top: 0;
    left: 0;
    z-index: 9999999;
    background-color: var(--darker);
    pointer-events: none;
  }

  .logo-wrapper {
    width: 50%;
    display: flex;
    gap: 1rem;
    font-size: 3rem;
    opacity: 0.7;
    align-items: center;
    justify-content: center;
  }

  .logo__reveal {
    opacity: 0;
    animation: rotate 10s infinite linear;
  }

  @keyframes rotate {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(360deg);
    }
  }

  @media (max-width: 768px) {
    .logo-wrapper {
      width: 100%;
      font-size: 2rem;
    }
  }
</style>
