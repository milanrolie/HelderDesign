<script>
  import { onMount } from 'svelte'
  import { gsap } from 'gsap'
  import { ScrollTrigger } from 'gsap/dist/ScrollTrigger'

  onMount(() => {
    gsap.registerPlugin(ScrollTrigger)

    // Select all sentenceScroll elements and animate each individually
    gsap.utils.toArray('#sentenceScroll').forEach((sentence) => {
      gsap.to(sentence, {
        scrollTrigger: {
          trigger: sentence, // Changed to trigger on each sentence
          start: 'top-=500',
          end: 'bottom',
        },
        duration: 1,
        y: 0,
        clipPath: 'polygon(0 0, 100% 0, 100% 100%, 0 100%)',
        ease: 'power4.out',
      })
    })
  })
</script>

<section class="about__container">
  <div class="text__container">
    <h2 class="about__title mobile-hide">
      <span id="sentenceScroll"> Helder is a design studio where we craft</span>
      <span id="sentenceScroll">
        conceptual light experiences by integrating
      </span>
      <span id="sentenceScroll">
        light, space, time, and various modalities
      </span>
      <span id="sentenceScroll"> into a cohesive whole. </span>
    </h2>

    <h2 class="about__title mobile-hide">
      <span id="sentenceScroll"> Our work is defined by the creation of </span>
      <span id="sentenceScroll"> contemporary fixtures where the impact </span>
      <span id="sentenceScroll"> on the overall experience is leading. </span>
      <span id="sentenceScroll"> </span>
      <span id="sentenceScroll"> </span>
      <span id="sentenceScroll"> </span>
    </h2>

    <h2 class="mobile-title desktop-hide">
      Helder is a design studio where we craft conceptual light experiences by
      integrating light, space, time, and various modalities into a cohesive
      whole. Our work is defined by the creation of contemporary fixtures where
      the impact on the overall experience is leading.
    </h2>

    <div class="line desktop-hide"></div>

    <div class="about__paragraphs">
      <p class="about__paragraph">
        We prioritize the intended experience over the object itself, believing
        that a strong conceptual foundation is essential. Our approach lies at
        the intersection of storytelling, design, and light, constantly
        exploring how light can transform and take on new forms in
        three-dimensional space.
      </p>
      <p class="about__paragraph">
        Founded by two Industrial Design graduates of Eindhoven University of
        Technology, Helder Design combines an understanding of design principles
        with practical expertise in event and experience production. By
        continuous dreaming and prototyping, we embrace the connection between
        art, design, and technology, emphasizing the act of experiencing.
      </p>
    </div>
  </div>

  <!-- <img class="about__image" src="src/lib/assets/image 6.png" alt="" /> -->
</section>

<style>
  .about__container {
    position: relative;
    display: grid;

    width: 100%;
    padding: var(--padding-large);
    padding-top: 25svh;
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

  .about__paragraphs {
    display: flex;
    gap: var(--padding-medium);
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.2em;
    color: var(--dark);
    width: 60%;
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
    }

    .mobile-title {
      display: block;
      font-size: 1.8rem;
      font-weight: 400;
      line-height: 1.2em;
      color: var(--dark);
      margin: 0;
    }

    .line {
      display: block;
      width: 100%;
      height: 1px;
      background-color: var(--dark);
      margin-top: var(--padding-medium);
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
      font-weight: 600;
    }

    .about__paragraphs {
      flex-direction: column;
      font-size: 0.7rem;
      font-weight: 400;
      line-height: 1.5em;
      color: var(--dark);
      width: 100%;
      margin: 0;
      max-width: 90%;
      gap: 0;
    }
  }
</style>
