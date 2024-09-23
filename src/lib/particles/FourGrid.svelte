<script>
  import image from "$lib/assets/image 6.png";
  import imageLeft from "$lib/assets/01_KarelAarts_Helder_Overig (3 of 3) (1).jpg";
  import imageRight from "$lib/assets/02_KarelAarts_Helder_DDW2024 (2 of 5).jpg";
  import imageBottomLeft from "$lib/assets/03_KarelAarts_Helder_DDW2024 (3 of 5).jpg";
  import imageBottomRight from "$lib/assets/04_KarelAarts_Helder_DDW2024 (5 of 5) (1).jpg";
</script>

<div class="fourgrid__container">
  <img class="grid__image" src={imageLeft} alt="" />
  <img class="grid__image" src={imageRight} alt="" />
  <img class="grid__image" src={imageBottomLeft} alt="" />
  <img class="grid__image" src={imageBottomRight} alt="" />
</div>

<style>
  .fourgrid__container {
    position: relative;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: 1fr 1fr;
    z-index: 10;
  }

  .grid__image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    aspect-ratio: 1/1;
    mix-blend-mode: lighten;
  }
</style>
