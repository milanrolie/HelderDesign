<script>
  import { gsap } from "gsap";
  import { onMount } from "svelte";
  import SiteHeader from "$lib/structures/SiteHeader.svelte";

  let threeLoaded = false;

  function handleThreeLoaded() {
    threeLoaded = true;
  }

  onMount(() => {
    gsap.to(".gsap-path", {
      duration: 1.5,
      opacity: 1,
      stagger: 0.05,
    });

    gsap.to(".sternfilms", {
      delay: 0,
      duration: 2,
      opacity: 1,
      ease: "power4.out",
    });

    gsap.from(".sternfilms", {
      delay: 0.5,
      "--progress": 1,
      duration: 2,
      ease: "power4.out",
    });

    gsap.to(".gsap-path", {
      delay: 2.5,
      duration: 1,
      opacity: 0,
      ease: "power4.out",
    });

    gsap.to(".sternfilms", {
      delay: 2.5,
      duration: 1,
      opacity: 0,
      ease: "power4.out",
    });

    if (threeLoaded) {
      gsap.to(".gsap-reveal", {
        delay: 3,
        duration: 1.5,
        ease: "power1.out",
        opacity: 0,
      });
    }
  });
</script>

<SiteHeader on:threeLoaded={handleThreeLoaded} />

<section class="gsap-reveal">
  <div class="logo-wrapper">
    <svg
      class="animated__logo"
      width="440"
      height="440"
      viewBox="0 0 440 440"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
    >
      <mask
        id="mask0_628_73"
        style="mask-type:luminance"
        maskUnits="userSpaceOnUse"
        x="0"
        y="0"
        width="440"
        height="440"
      >
        <path
          d="M220.396 439.028C99.4239 439.028 0.896118 340.5 0.896118 219.528C0.896118 98.5558 99.4239 0.0280762 220.396 0.0280762C341.368 0.0280762 439.896 98.5558 439.896 219.528C439.896 340.5 341.368 439.028 220.396 439.028ZM220.396 98.1754C153.443 98.1754 99.0434 152.575 99.0434 219.528C99.0434 286.481 153.443 340.881 220.396 340.881C287.349 340.881 341.749 286.481 341.749 219.528C341.749 152.575 287.349 98.1754 220.396 98.1754Z"
          fill="white"
        />
      </mask>
      <g mask="url(#mask0_628_73)">
        <path
          d="M-192.355 -318H877.679V716.427H-192.355V-318Z"
          fill="url(#pattern0_628_73)"
        />
      </g>
      <mask
        id="mask1_628_73"
        style="mask-type:luminance"
        maskUnits="userSpaceOnUse"
        x="0"
        y="0"
        width="440"
        height="440"
      >
        <path
          d="M220.396 439.028C99.4239 439.028 0.896118 340.5 0.896118 219.528C0.896118 98.5558 99.4239 0.0280762 220.396 0.0280762C341.368 0.0280762 439.896 98.5558 439.896 219.528C439.896 340.5 341.368 439.028 220.396 439.028ZM220.396 98.1754C153.443 98.1754 99.0434 152.575 99.0434 219.528C99.0434 286.481 153.443 340.881 220.396 340.881C287.349 340.881 341.749 286.481 341.749 219.528C341.749 152.575 287.349 98.1754 220.396 98.1754Z"
          fill="white"
        />
      </mask>
      <g mask="url(#mask1_628_73)">
        <path
          d="M-343 -96.1411H480.524V716.427H-343V-96.1411Z"
          fill="url(#pattern1_628_73)"
        />
      </g>
      <defs>
        <pattern
          id="pattern0_628_73"
          patternContentUnits="objectBoundingBox"
          width="1"
          height="1"
        >
          <use
            xlink:href="#image0_628_73"
            transform="scale(0.000851064 0.000878735)"
          />
        </pattern>
        <pattern
          id="pattern1_628_73"
          patternContentUnits="objectBoundingBox"
          width="1"
          height="1"
        >
          <use
            xlink:href="#image1_628_73"
            transform="scale(0.00110619 0.00111607)"
          />
        </pattern>
      </defs>
    </svg>
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

  .gsap-path {
    opacity: 0;
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

  svg {
    opacity: 1;
  }

  .sternfilms {
    clip-path: polygon(
      0 0,
      calc((1 - var(--progress)) * 100%) 0,
      calc((1 - var(--progress)) * 100%) 100%,
      0% 100%
    );
    opacity: 0;
  }

  @media (max-width: 768px) {
    .logo-wrapper {
      width: 100%;
      font-size: 2rem;
    }
  }
</style>
