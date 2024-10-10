<script>
  import { onMount } from "svelte";
  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/dist/ScrollTrigger";

  import image from "$lib/assets/03_KarelAarts_Helder_DDW2024 (3 of 5).jpg";
  import Marquee from "../particles/Marquee.svelte";

  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);

    const text = document.querySelector(
      ".schermlicht__container  .schermlicht__title"
    );
    // Split text into words instead of characters
    const words = text.innerText
      .split(" ")
      .map((word) => `<span>${word} </span>`) // Add a space after each word to maintain original spacing
      .join("");
    text.innerHTML = words;

    const animation = gsap.timeline({
      scrollTrigger: {
        trigger: ".schermlicht__title",
        start: "top" - window.innerHeight,
        end: "top-=200",
        scrub: true,
      },
    });

    gsap.utils
      .toArray(".text__container .schermlicht__title span")
      .forEach((word, i) => {
        animation.to(
          word,
          {
            color: "#ecece2",
            duration: 0,
            ease: "none",
          },
          i * 0.05
        );
      });

    // gsap.from(".schermlicht__image", {
    //   opacity: 0,
    //   ease: "none",
    //   scrollTrigger: {
    //     trigger: ".schermlicht__image",
    //     start: "top-=200%",
    //     end: "top-=50%",
    //     scrub: true,
    //   },
    // });
  });
</script>

<div class="marquee__container">
  <Marquee />
</div>
<section class="schermlicht__container" id="schermlicht">
  <p class="project__tags">Schermlicht, project 1</p>
  <div class="line"></div>
  <div class="text__container">
    <h2 class="schermlicht__title">
      Schermlicht is our latest exploration into redefining the role of LED
      screens in day-to-day environments. In a world dominated by repetitive use
      of large displays, we see opportunities for subtle yet expressive light
      fixtures.
    </h2>
  </div>
  <img class="schermlicht__image" src={image} alt="" />
  <div class="paragraph__container">
    <p class="paragraph__title">
      Our aim is to develop new light effects that offer a more immersive
      experience, shifting the screen’s function from capturing our world to
      actively taking part in the spatial environment, ultimately enriching the
      sensorial experience.
    </p>

    <p class="schermlicht__paragraph">
      With Schermlicht, we envision LED screens as spatial light sources that
      create three-dimensional light volumes, allowing light to move beyond the
      flat, two-dimensional plane and interact with the physical space.
    </p>
    <p class="paragraph__tag">
      Schermlicht will be presented at the Dutch Design Week Eindhoven from
      October 19th till 27th. You can find us at Sectie C, Hall 4. See the DDW
      website for more information: <a
        href="https://ddw.nl/nl/programma/12272/schermlicht "
        >Dutch Design Week</a
      >
    </p>
  </div>
</section>

<!-- <FourGrid /> -->

<style>
  .marquee__container {
    position: relative;
    width: 100%;
    background-color: var(--light);
    overflow: hidden;
  }

  .schermlicht__container {
    position: relative;
    background-color: var(--darker);
    height: auto;
    padding: var(--padding-large);
    padding-bottom: 25svh;
  }

  .project__tags {
    font-size: clamp(1rem, 1vw, 2rem);
    font-weight: 400;
    color: var(--grey-dark);
    margin: 0;
    text-transform: uppercase;
    text-align: right;
  }

  .line {
    position: relative;
    width: 100%;
    height: 0.75px;
    background-color: var(--grey-dark);
    top: 0;
    transform: translateY(-50%);
    margin: var(--padding-medium) 0;
  }

  .text__container {
    display: grid;

    gap: var(--padding-large);
    grid-template-columns: 2fr 1fr;
  }

  .schermlicht__title {
    font-size: clamp(2rem, 3vw, 5rem);
    font-weight: 400;
    line-height: 1.2em;
    margin: 0;
    color: var(--grey-dark);
  }

  .schermlicht__image {
    position: relative;
    height: 100%;
    width: 80%;
    object-fit: cover;
    mix-blend-mode: lighten;
    margin-left: 10%;
    transform: translateY(10rem);
    transform: scaleX(-1);
    margin-bottom: 10rem;
  }

  .paragraph__container {
    color: var(--grey);
    max-width: 50%;
  }

  .paragraph__title {
    font-size: 2rem;
    font-weight: 400;
    margin: 0;
  }

  .schermlicht__paragraph {
    font-size: 1.5rem;
    font-weight: 300;
  }

  .paragraph__tag {
    font-size: 0.9rem;
    font-weight: 400;
    color: var(--grey-dark);
    margin-top: var(--padding-large);
    max-width: 60%;
  }

  @media (max-width: 768px) {
    .schermlicht__container {
      position: relative;
      background-color: var(--darker);
      height: auto;
      padding: var(--padding-medium);
    }

    .text__container {
      grid-template-columns: 1fr;
    }

    .project__tags {
      font-size: clamp(0.8rem, 1vw, 1rem);
    }

    .line {
      margin: var(--padding-small) 0;
    }

    .schermlicht__title {
      font-size: clamp(1.5rem, 3vw, 4rem);
    }

    .schermlicht__image {
      width: 100%;
      height: 100%;
      margin-left: 0;
      margin: 5rem 0;
      transform: translateY(0);
      margin-bottom: 0;
    }

    .paragraph__container {
      max-width: 100%;
    }

    .paragraph__title {
      font-size: 1.2rem;
    }

    .schermlicht__paragraph {
      font-size: 1rem;
    }

    .paragraph__tag {
      font-size: 0.8rem;
      max-width: 100%;
    }
  }
</style>
