<script>
  import Marquee from "../particles/Marquee.svelte";

  import image from "$lib/assets/53627131563_dd404e869a_o (1) (1).jpg";
  import leftImage from "$lib/assets/53627133473_eecef7fe9e_o (1).jpg";
  import rightImage from "$lib/assets/53627130833_1f63365729_o.jpg";
</script>

<div class="overflow__fix">
  <section class="capsulated" id="capsulated">
    <Marquee />
    <p class="project__tags">Capsulated, project 1</p>
    <div class="line"></div>

    <img class="capsulated__image" src={image} alt="" />
    <div class="text__container">
      <h2 class="capsulated__title">
        With our first project, Capsulated, we aim to capture the immense power
        of the sun in a single light fixture.
      </h2>
      <p class="capsulated__paragraph">
        Inspired by the awe of sunrises and sunsets, Capsulated evokes a sense
        of wonder through its dynamic design, where light refracts off a Perspex
        plate, mimicking the subtle movement of the sun. The double-sided,
        modular structure allows light to flow deeply into any environment,
        offering tranquility and adapting to different settings. Capsulated
        redefines how light and space interact, creating a deeply personal,
        sensory experience.
      </p>
    </div>

    <div class="image__grid">
      <img class="grid__image" src={leftImage} alt="" />

      <img class="grid__image" src={rightImage} alt="" />
    </div>
  </section>
</div>

<style>
  .overflow__fix {
    overflow: hidden;
  }

  .capsulated {
    position: relative;
    width: 100%;
    background-color: var(--light);
    padding: var(--padding-large);
  }

  .project__tags {
    font-size: clamp(1rem, 1vw, 2rem);
    font-weight: 400;
    color: var(--dark);
    margin-top: var(--padding-large);
    text-transform: uppercase;
    text-align: right;
  }

  .line {
    position: relative;
    width: 100%;
    height: 0.75px;
    background-color: var(--dark);
    top: 0;
    transform: translateY(-50%);
    margin: var(--padding-medium) 0;
  }

  .capsulated__image {
    width: 100%;
    height: 100%;
  }

  .text__container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: var(--padding-large);
    align-items: flex-end;
    /* margin: 10rem 0; */
    margin-bottom: var(--space);
    padding: var(--padding-large);
  }

  .capsulated__title {
    font-size: clamp(2rem, 3vw, 4rem);
    font-weight: 400;
    color: var(--dark);
    line-height: 1.1em;
    margin-bottom: 10rem;
  }

  .capsulated__paragraph {
    font-size: clamp(1rem, 1vw, 1.5rem);
    font-weight: 400;
    color: var(--dark);
    margin: 0;
    margin-right: 5rem;
  }

  .image__grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: var(--padding-large);
    margin-top: var(--padding-large);
  }

  .grid__image {
    width: 100%;
    height: 100%;
  }

  @media (max-width: 768px) {
    .capsulated {
      padding: var(--padding-medium);
    }

    .text__container {
      grid-template-columns: 1fr;
    }

    .capsulated__title {
      margin-bottom: 0;
    }

    .capsulated__paragraph {
      margin-right: 0;
      font-size: 0.9rem;
    }

    .image__grid {
      grid-template-columns: 1fr;
      gap: var(--padding-medium);
    }
  }
</style>
