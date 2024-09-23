<!-- <script>
  import { onMount } from "svelte";
  import gsap from "gsap";
  import ScrollTrigger from "gsap/dist/ScrollTrigger";

  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);

    gsap.to("#sentenceScroll", {
      scrollTrigger: {
        trigger: "#sentenceScroll",
        start: "top+=500",
        end: "bottom",
        toggleActions: "play none none reverse",
      },
      duration: 1.5,
      delay: 0.3,
      y: 0,
      clipPath: "polygon(0 0, 100% 0, 100% 100%, 0 100%)",
      stagger: 0.2,
      ease: "power4.out",
    });
  });
</script> -->
