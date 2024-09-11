<script>
  import Introduction from "../lib/structures/Introduction.svelte";
  import Navigation from "$lib/structures/Navigation.svelte";
  import Three from "../lib/structures/Three.svelte";
  import About from "../lib/structures/About.svelte";
  import Footer from "../lib/structures/Footer.svelte";
  import IntroAnimation from "../lib/fragments/IntroAnimation.svelte";
</script>

<IntroAnimation />

<div class="fixed">
  <Navigation />
  <Introduction />
  <Three />
</div>

<About />
<Footer />

<style>
  .fixed {
    position: sticky;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
  }
</style>
