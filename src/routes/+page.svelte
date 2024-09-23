<script>
  import About from "../lib/structures/About.svelte";
  import Footer from "../lib/structures/Footer.svelte";
  import IntroAnimation from "../lib/fragments/IntroAnimation.svelte";
  import { createEventDispatcher } from "svelte";
  import SiteHeader from "../lib/structures/SiteHeader.svelte";
  import FullImage from "$lib/particles/FullImage.svelte";
  import Schermlicht from "../lib/structures/Schermlicht.svelte";
  import Capsulated from "../lib/structures/Capsulated.svelte";
</script>

<IntroAnimation />
<About />
<Capsulated />
<FullImage />
<Schermlicht />
<Footer />
