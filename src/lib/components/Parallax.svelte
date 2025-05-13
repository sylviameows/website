<script lang="ts">
  let y = $state(0)

  let { children } = $props();

  let page: HTMLDivElement

  function scroll() {
    window.scrollTo({top: page.offsetTop * 0.75, behavior: 'smooth'})
  }
</script> 

<svelte:window bind:scrollY={y} />

{#if y*0.005 < 1}
<div style="display: flex; width: 100%; justify-content: center;">
  <button class="scroll" onclick={scroll} style="opacity: {1 - Math.min(y*0.005, 1)};">
    <p>continue</p>
    <p class="bobbing">v</p>
  </button>
</div>
{/if}

<div id="parallax">
  <div class="sky smooth" style="transform: translate(0,{-y * 0.1}px);"> </div>
  <div class="far_clouds smooth" style="transform: translate(0,{-y * 0.2}px);"> </div>
  <div class="near_clouds smooth" style="transform: translate(0,{-y * 0.3}px);"> </div>
  <div class="far_mountains smooth" style="transform: translate(0,{-y * 0.4}px);"> </div>
  <div class="near_mountains smooth" style="transform: translate(0,{-y * 0.5}px);"> </div>
  <div class="trees smooth" style="transform: translate(0,{-y * 0.7}px);"> 
    <div bind:this={page} id="page" style="smooth">
      {@render children()}
    </div>
  </div>
</div>

<style>
  .smooth {
    transition: 25ms cubic-bezier(0.165, 0.84, 0.44, 1);
  }

  .scroll {
    display: flex;
    flex-direction: column;
    position: absolute;
    align-items: center;
    width: 100%;
    max-width: fit-content;
    bottom: 3em;

    background: none;
    border: 0;
  }

  .scroll p {
    font: 2em "CutePixel";
    color: aliceblue;

    margin: 0;
  }

  .bobbing {
    animation: bob 2s infinite;
  }

  @keyframes bob {
    0% {
      transform: translateY(0);
    }

    50% {
      transform: translateY(0.25em);
    }

    100% {
      transform: translateY(0);
    }
  }

  #page {
    position: relative;
    top: 100%;

    height: auto !important;
    min-height: 75%;
  }

  #parallax {
    position: absolute;
    z-index: -10;
  }

  #parallax div {
    position: absolute;
    width: 100vw;
    height: 100vh;

    background-repeat: repeat-x;
    background-size: auto 100vh;
    background-position-x: center;

    image-rendering: pixelated;
  }

  #parallax .sky {
    background-image: url('$lib/assets/parallax/sky.png');
    z-index: -10;
  }
  #parallax .far_clouds {
    background-image: url('$lib/assets/parallax/far-clouds.png');
    z-index: -9;

    top: 10vh;
  }
  #parallax .near_clouds {
    background-image: url('$lib/assets/parallax/near-clouds.png');
    z-index: -8;

    top: 20vh;
  }
  #parallax .far_mountains {
    background-image: url('$lib/assets/parallax/far-mountains.png');
    z-index: -7;

    top: 30vh;
  }
  #parallax .near_mountains {
    background-image: url('$lib/assets/parallax/mountains.png');
    z-index: -6;

    top: 40vh;
  }
  #parallax .trees {
    background-image: url('$lib/assets/parallax/trees.png');
    z-index: -5;

    top: 50vh;
  }
</style>