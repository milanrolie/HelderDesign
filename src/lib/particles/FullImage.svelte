<script>
  import { onMount } from "svelte";
  import { gsap } from "gsap";
  import image from "$lib/assets/53627262729_445f4500d7_o (1).jpg";

  onMount(() => {
    gsap.from(".parrallax__image", {
      y: "-10%",
      scale: 1.1,
      ease: "none",
      scrollTrigger: {
        trigger: ".parrallax__figure",
        start: "top-=100%",
        end: "bottom+=100%",
        scrub: true,
      },
    });
  });
</script>

<figure class="parrallax__figure">
  <img class="parrallax__image" src={image} alt="" />
</figure>

<style>
  .parrallax__figure {
    position: relative;
    overflow: hidden;
    aspect-ratio: 16/9;
    width: 100%;
    z-index: 10;
  }

  img {
    position: absolute;
    width: 100%;
    height: 150%;
    inset: 0;
    object-fit: cover;
    transform: translateY(-30%);
  }

  @media (max-width: 768px) {
    .parrallax__figure {
      aspect-ratio: 3/4;
      width: 100%;
    }
  }
</style>
