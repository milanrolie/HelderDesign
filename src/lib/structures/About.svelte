<script>
  import { onMount } from "svelte";
  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/dist/ScrollTrigger";

  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);
    const text = document.querySelector(".about__container .about__title");
    // Split text into words instead of characters
    const words = text.innerText
      .split(" ")
      .map((word) => `<span>${word} </span>`) // Add a space after each word to maintain original spacing
      .join("");
    text.innerHTML = words;

    const animation = gsap.timeline({
      scrollTrigger: {
        trigger: ".about__container",
        start: "top ",
        end: "center",
        scrub: true,
      },
    });

    // Animate each word span
    gsap.utils
      .toArray(".about__container .about__title span")
      .forEach((word, i) => {
        animation.to(
          word,
          {
            color: "#efefef", // Change to desired color
            duration: 0,
            ease: "none",
          },
          i * 0.05 // Adjusted stagger time for words
        );
      });
  });
</script>

<section class="about__container">
  <div class="text__container">
    <h2 class="about__title">
      At Helder, we explore the boundaries of light and design to create
      immersive experiences that go beyond the ordinary.
    </h2>
    <p class="about__paragraph">
      By blending light, space, and time with innovative thinking, we design not
      just objects, but holistic experiences that resonate deeply with those who
      encounter them. Our work is a continuous journey of exploration and
      experimentation, driven by a desire to redefine the relationship between
      technology, design, and human experience.
    </p>
  </div>

  <img class="about__image" src="src/lib/assets/image 6.png" alt="" />
</section>

<style>
  .about__container {
    position: relative;
    display: grid;
    height: 200vh;
    width: 100%;
    padding: var(--padding-large);
    gap: var(--padding-large);
    grid-template-columns: 2fr 1fr;
    background-color: var(--dark);
  }

  .text__container {
    top: var(--padding-large);
    position: sticky;
    height: 100vh;
    display: flex;
    flex-direction: column;
    gap: var(--padding-large);
  }

  .about__title {
    font-size: 4rem;
    font-weight: 400;
    line-height: 1.1em;
    color: var(--grey-dark);
    margin: 0;
  }

  .about__paragraph {
    font-size: 1rem;
    font-weight: 300;
    line-height: 1.2em;
    color: var(--grey);
    width: 80%;
  }

  img {
    position: sticky;
    top: var(--padding-large);
    width: 100%;
    object-fit: cover;
  }

  @media (max-width: 768px) {
    .about__container {
      grid-template-columns: 1fr;
      padding: var(--padding-small);
    }

    p {
      font-size: 1rem;
      width: 100%;
    }
  }
</style>
