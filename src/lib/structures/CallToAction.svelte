<script>
</script>

<section class="call-to-action">
  <h3 class="call-to-action__title">
    Ready to <span id="sentenceScroll"> start a</span> new project?
  </h3>
  <a href="mailto:info@helderdesign.studio" class="call-to-action__button"
    >Send an email</a
  >
</section>

<style>
  .call-to-action {
    position: relative;
    width: 100%;
    height: 70vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: var(--padding-large);
    background-color: var(--light);
    padding: var(--padding-large);
  }

  .call-to-action__title {
    font-size: clamp(2rem, 15vw, 12rem);

    font-weight: 800;
    color: var(--dark);
    line-height: 0.8em;
    margin: 0;
    text-transform: uppercase;
  }

  .call-to-action__button {
    font-size: 1rem;
    font-weight: 400;
    color: var(--dark);
    background-color: var(--light);
    border: 1px solid var(--dark);
    padding: var(--padding-medium) var(--padding-large);
    border-radius: 0;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .call-to-action__button:hover {
    background-color: var(--dark);
    color: var(--light);
  }
</style>
