<script>
  import { onMount } from "svelte";

  import Introduction from "$lib/structures/Introduction.svelte";
  import Navigation from "$lib/structures/Navigation.svelte";
  import Three from "$lib/structures/Three.svelte";

  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  onMount(() => {
    dispatch("threeLoaded");
  });
</script>

<div class="fixed">
  <Navigation />
  <Introduction />
  <Three />
</div>

<style>
  .fixed {
    position: sticky;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
  }

  @media (max-width: 768px) {
    .fixed {
      position: relative;
    }
  }
</style>
