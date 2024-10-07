<script>
  import { onMount } from "svelte";
  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/dist/ScrollTrigger";

  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);

    // const text = document.querySelector(".about__container .about__title");
    // // Split text into words instead of characters
    // const words = text.innerText
    //   .split(" ")
    //   .map((word) => `<span>${word} </span>`) // Add a space after each word to maintain original spacing
    //   .join("");
    // text.innerHTML = words;

    // const animation = gsap.timeline({
    //   scrollTrigger: {
    //     trigger: ".about__title",
    //     start: "top-=100",
    //     end: "center",
    //     scrub: false,
    //   },
    // });

    // gsap.utils
    //   .toArray(".about__container .about__title span")
    //   .forEach((word, i) => {
    //     animation.to(
    //       word,
    //       {
    //         color: "#1E1E1E",
    //         duration: 0,
    //         ease: "none",
    //       },
    //       i * 0.05
    //     );
    //   });

    gsap.to("#sentenceScroll", {
      scrollTrigger: {
        trigger: ".about__title",
        start: "top-=500",
        end: "bottom",
      },
      duration: 1,
      y: 0,
      clipPath: "polygon(0 0, 100% 0, 100% 100%, 0 100%)",
      stagger: 0.08,
      ease: "power4.out",
    });
  });
</script>

<section class="about__container">
  <div class="text__container">
    <h2 class="about__title">
      <span id="sentenceScroll"> At Helder, we explore the boundaries</span>
      <span id="sentenceScroll">
        of light and design to create conceptual
      </span>
      <span id="sentenceScroll">
        experiences that go beyond the ordinary.
      </span>
      <span id="sentenceScroll"> </span>
    </h2>

    <h2 class="about__title">
      <span id="sentenceScroll"> By blending light, space, and time with </span>
      <span id="sentenceScroll"> innovative thinking, we design not just </span>
      <span id="sentenceScroll"> objects, but holistic experiences that </span>
      <span id="sentenceScroll">
        resonate deeply with those who encounter
      </span>
      <span id="sentenceScroll">them. </span>
    </h2>
    <p class="about__paragraph">
      Founded by two Industrial Design graduates of Eindhoven University of
      Technology, Helder Design combines an understanding of design principles
      with practical expertise in event and experience production. By continuous
      dreaming and prototyping, we embrace the connection between art, design,
      and technology, emphasizing the act of experiencing.
    </p>
  </div>

  <!-- <img class="about__image" src="src/lib/assets/image 6.png" alt="" /> -->
</section>

<style>
  .about__container {
    position: relative;
    display: grid;

    width: 100%;
    padding: var(--padding-large);
    padding-top: 25vh;
    gap: var(--padding-large);
    grid-template-columns: 4fr 1fr;
    background-color: var(--light);
    color: var(--dark);
  }

  .text__container {
    top: var(--padding-large);
    height: 100svh;
    display: flex;
    flex-direction: column;
    gap: var(--padding-large);
  }

  .about__title {
    font-size: clamp(2rem, 3vw, 5rem);
    font-weight: 400;
    line-height: 1.2em;
    color: var(--dark);
    margin: 0;
  }

  .about__paragraph {
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.2em;
    color: var(--dark);
    width: 40%;
  }

  img {
    position: absolute;
    bottom: var(--padding-large);
    right: var(--padding-large);
    width: 20rem;
    object-fit: cover;
    border-radius: 0;
    aspect-ratio: 3/4;
  }

  @media (max-width: 768px) {
    .about__container {
      grid-template-columns: 1fr;
      padding: var(--padding-medium);
      height: 60svh;
    }

    p {
      font-size: 1rem;
      width: 100%;
    }

    .text__container {
      gap: var(--padding-small);
    }

    .about__title {
      font-size: clamp(1.1rem, 2vw, 3rem);
    }

    .about__paragraph {
      font-size: 0.9rem;
      font-weight: 400;
      line-height: 1.2em;
      color: var(--dark);
      width: 100%;
      /* padding-left: 10rem; */
      margin-top: 4rem;
      max-width: 70%;
    }
  }
</style>
