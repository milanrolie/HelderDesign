<script>
  import { onMount } from "svelte";
  import gsap from "gsap";
  import ScrollTrigger from "gsap/dist/ScrollTrigger";

  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);

    gsap.from(".title__container span, .events__container .event, circle", {
      opacity: 0,
      stagger: 0.2,
      ease: "power1.inOut",
      duration: 1,
      delay: 3.5,
    });

    gsap.to(".title__container span, .events__container .event, nav, circle", {
      scrollTrigger: {
        trigger: ".title__container",
        start: "top+=100 ",
        end: "center",
        scrub: true,
      },
      opacity: 0,
      y: -50,
      stagger: 0.2,
    });
  });
</script>

<section class="title__container">
  <svg
    width="59"
    height="59"
    viewBox="0 0 59 59"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <circle cx="29.5" cy="29.5" r="23.5" stroke="#e7e7be" stroke-width="12" />
  </svg>

  <h2>
    <span> Designing light, crafting conceptual </span>
    <span> experiences that transform spaces.</span>
  </h2>
</section>

<div class="events__container">
  <div class="event">
    <h3 class="event__title">PUIN @ THE POOL</h3>
    <p class="event__location">Sectie c, Eindhoven</p>
    <p class="event__date">28 September 2024</p>
  </div>

  <div class="event">
    <h3 class="event__title">DUTCH DESIGN WEEK</h3>
    <p class="event__location">Sectie c, Eindhoven</p>
    <p class="event__date">19 - 27 October 2024</p>
  </div>
</div>

<style>
  .title__container {
    position: absolute;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    width: 100%;
    z-index: 10;
    background-color: rgba(255, 255, 255, 0);
    pointer-events: none;
    gap: 1rem;
  }

  h2 {
    font-size: 2rem;
    font-weight: 300;
    color: var(--light);
    line-height: 1.1em;
  }

  h2 span {
    display: block;
  }

  .events__container {
    position: absolute;
    bottom: var(--padding-medium);
    left: var(--padding-large);
    display: flex;
    gap: var(--padding-large);
    color: var(--light);
    z-index: 10;
  }

  .event {
  }

  .event__title {
    font-size: 1rem;
    font-weight: 500;
  }

  .event__location {
    font-size: 0.9rem;
    font-weight: 300;
    line-height: 0.5em;
  }

  .event__date {
    font-size: 0.8rem;
    font-weight: 300;
    line-height: 0.5em;
  }

  @media (max-width: 768px) {
    .title__container {
      gap: 0.5rem;
    }

    h2 {
      font-size: 1rem;
    }

    .events__container {
      gap: var(--padding-small);
      bottom: var(--padding-small);
      left: var(--padding-small);
    }

    .event__title {
      font-size: 0.8rem;
    }

    .event__location {
      font-size: 0.7rem;
    }

    .event__date {
      font-size: 0.6rem;
    }

    svg {
      width: 30px;
      height: 30px;
    }
  }
</style>
