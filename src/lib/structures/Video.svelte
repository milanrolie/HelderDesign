<script>
  let video
  let muted = true

  import videoSrc from '$lib/assets/schermlicht.webm'

  function toggleMute() {
    muted = !muted
    if (video) {
      video.muted = muted
    }
  }
</script>

<div class="video__wrapper">
  <video bind:this={video} src={videoSrc} {muted} autoplay loop playsinline
  ></video>

  <button class="mute-btn" on:click={toggleMute}>
    {#if muted}
      <svg viewBox="0 0 163 163" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle opacity="0.7" cx="81.5" cy="81.5" r="81.5" fill="" />
        <path
          d="M90.125 53.8066V108.932C90.125 113.494 85.1875 116.244 81.3125 113.869L53.625 94.5566V96.4941H42V68.8066H53.625V70.7441L81.0625 49.0566C84.875 46.3691 90.125 49.1191 90.125 53.8066ZM122 90.2441L101.812 69.9941L97.625 74.1816L117.813 94.3691L122 90.2441ZM101.812 94.4316L122 74.2441L117.813 70.0566L97.5625 90.2441L101.812 94.4316Z"
          fill="white"
        />
      </svg>
    {:else}
      <svg viewBox="0 0 163 163" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle opacity="0.7" cx="81.5" cy="81.5" r="81.5" fill="" />
        <path
          d="M90.0781 56.8126V111.863C90.0781 116.379 85.0977 119.168 81.2461 116.777L53.6211 97.5196V99.4454H42V71.8204H53.6211V73.7462L81.0469 52.0313C84.832 49.3751 90.0781 52.1642 90.0781 56.8126ZM96.7188 114.652V110.402C111.063 110.402 122.75 98.7149 122.75 84.3712C122.75 70.0274 111.063 58.3399 96.7188 58.3399V54.0899C113.387 54.0899 127 67.7032 127 84.3712C127 101.039 113.387 114.652 96.7188 114.652ZM96.7188 105.356V101.106C105.949 101.106 113.52 93.6017 113.52 84.3048C113.52 75.0079 105.949 67.5704 96.7188 67.5704V63.3204C108.34 63.3868 117.703 72.8165 117.703 84.3712C117.703 95.9259 108.34 105.356 96.7188 105.356ZM96.7188 96.5899V92.3399C101.102 92.3399 104.688 88.754 104.688 84.3712C104.688 79.9884 101.102 76.4024 96.7188 76.4024V72.1524C103.426 72.1524 108.938 77.5977 108.938 84.3712C108.938 91.1446 103.426 96.5899 96.7188 96.5899Z"
          fill="white"
        />
      </svg>
    {/if}
  </button>
</div>

<style>
  .video__wrapper {
    position: relative;
  }

  video {
    width: 100%;
    height: 100%;
    object-fit: cover;
    background-color: var(--dark);
    z-index: 10;
    transform: translateY(5px);
  }

  .mute-btn {
    position: absolute;
    bottom: var(--padding-medium);
    right: var(--padding-medium);
    background: rgba(0, 0, 0, 0.5);
    border: none;
    border-radius: 50%;
    width: 5rem;
    height: 5rem;
    cursor: pointer;
    color: white;
    font-size: 1.5rem;
    transition: background-color 0.2s;
    opacity: 0.8;
  }

  .mute-btn:hover {
    background: rgba(0, 0, 0, 0.7);
  }
</style>
