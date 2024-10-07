<script>
  import image1 from "$lib/assets/53627130833_1f63365729_o.jpg";
  import image2 from "$lib/assets/02_KarelAarts_Helder_DDW2024 (2 of 5).jpg";
  import image3 from "$lib/assets/image 6.png";

  const images = [image1, image2, image3];

  import { onMount } from "svelte";
  import gsap from "gsap";

  import { Draggable } from "gsap/dist/Draggable";

  onMount(() => {
    gsap.registerPlugin(Draggable);

    Draggable.create(".image__grid", {
      type: "x",
      bounds: ".image__grid",
      inertia: true,
    });
  });
</script>

<div class="image-slider">
  <div class="image__grid">
    {#each images as image}
      <img src={image} alt="" class="image__grid__image" />
    {/each}
  </div>
</div>

<style>
  .image-slider {
    position: relative;
    width: auto;
    overflow: hidden;
    background-color: var(--light);
    padding: var(--padding-large);
    overflow: hidden;
  }

  .image__grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: var(--padding-large);
    cursor: grab;
    width: max-content;
  }

  .image__grid:active {
    cursor: grabbing;
  }

  .image__grid__image {
    width: 40vw;
    aspect-ratio: 3/4;
    display: block;
  }

  @media (max-width: 768px) {
    .image__grid__image {
      width: 80vw;
    }

    .image__grid__image {
      height: 100%;

      aspect-ratio: 3/4;
      display: block;
    }

    .image__grid {
      gap: var(--padding-small);
    }
  }
</style>
