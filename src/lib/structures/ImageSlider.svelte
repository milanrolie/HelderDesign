<script>
  import image1 from '$lib/assets/53627130833_1f63365729_o.jpg'
  import image2 from '$lib/assets/53627133473_eecef7fe9e_o (1).jpg'
  import image3 from '$lib/assets/image 6.png'

  import 'swiper/css'
  import 'swiper/css/pagination'

  const images = [image1, image2, image3]

  import { register } from 'swiper/element/bundle'
  import { onMount } from 'svelte'

  register()

  let swiper

  onMount(() => {
    const swiperEl = document.querySelector('swiper-container')
    const swiperParams = {
      pagination: true,
      paginationClickable: true,

      slidesPerView: 2.5,
      spaceBetween: 20,
      breakpoints: {
        768: {
          slidesPerView: 2.5,
          spaceBetween: 30,
        },
      },
      injectStyles: [
        `
        :host .swiper-pagination-bullet {
          background-color: var(--dark);
        }
      `,
      ],
    }
    Object.assign(swiperEl, swiperParams)
    swiperEl.initialize()
    swiper = swiperEl
  })

  function slideNext() {
    swiper?.swiper?.slideNext()
  }

  function slidePrev() {
    swiper?.swiper?.slidePrev()
  }
</script>

<div class="image-slider">
  <div class="navigation-buttons">
    <button on:click={slidePrev} class="nav-button"
      ><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24"
        ><path
          d="m12.718 4.707-1.413-1.415L2.585 12l8.72 8.707 1.413-1.415L6.417 13H20v-2H6.416l6.302-6.293z"
        /></svg
      ></button
    >
    <button on:click={slideNext} class="nav-button"
      ><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24"
        ><path
          d="m11.293 19.293 1.414 1.414L21.414 12l-8.707-8.707-1.414 1.414L17.586 11H4v2h13.584l-6.293 6.293z"
        /></svg
      ></button
    >
  </div>
  <swiper-container pagination="true">
    {#each images as image}
      <swiper-slide>
        <img src={image} alt="" class="image__grid__image" />
      </swiper-slide>
    {/each}
  </swiper-container>
</div>

<style lang="scss">
  .image-slider {
    position: relative;
    padding: var(--padding-large) 0 var(--padding-large) var(--padding-small);
    background-color: var(--light);

    @media (max-width: 768px) {
      padding: var(--padding-medium);
    }
  }

  swiper-container {
    width: 100%;
    height: 100%;
  }

  swiper-slide {
    text-align: center;
    font-size: 18px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: grab;
  }

  swiper-slide img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
    aspect-ratio: 3/4;
  }

  .navigation-buttons {
    display: flex;
    gap: 1rem;
    justify-content: flex-end;
    padding: var(--padding-large);

    @media (max-width: 768px) {
      padding: var(--padding-small);
    }
  }

  .nav-button {
    padding: 1rem;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: var(--light);
    border: 1px solid var(--dark);
    cursor: pointer;
    transition: all 0.2s ease;
    border-radius: 50%;
    aspect-ratio: 1/1;

    &:hover {
      background-color: var(--dark);
      color: var(--light);
      fill: var(--light);
    }

    @media (max-width: 768px) {
      padding: 0.5rem;
    }
  }
</style>
