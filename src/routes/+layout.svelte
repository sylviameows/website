<script lang="ts">
  import Parallax from "$lib/components/Parallax.svelte";

	let { children } = $props();

  let char = $state("=")
  let button: HTMLButtonElement
  let menu: HTMLDivElement

  function nav() {
    if (char == "=") {
      char = "x"

      button.style = "transform: rotate3d(0, 1, 0, 0.5turn);"
      menu.style = "transform: scale(1);"

    } else {
      char = "="

      button.style = "transform: rotate3d(0,0,0, 0.5turn);"
      menu.style = "transform: scale(0);"
    }
  }
</script>

<nav id="navigation">
  <a href="/" class="home">sylviameo.ws</a>
  <button bind:this={button} onclick={nav}>{char}</button>
  <div bind:this={menu} style="transform: scale(0);" class="menu">
    <a href="/projects/arcator" class="home" onclick={nav}>arcator</a>
    <a href="/projects/amayi" class="home" onclick={nav}>amayi</a>
    <a href="/projects/flask" class="home" onclick={nav}>flask</a>
  </div>
</nav>

{@render children()}

<style>
  @font-face {
    font-family: 'CutePixel';
    font-weight: 400;
    font-style: normal;
    src: url("$lib/fonts/CutePixel.ttf") format('truetype')
  }

  :global(body) {
    margin: 0;
    padding: 0;
    
    overflow-x: hidden;

    font-family: 'CutePixel';

    background-color: #2C2546;
    color: aliceblue;
  }

  #navigation {
    position: fixed;
    top: 0;
    width: calc(100vw - 2em);
    display: flex;
    justify-content: space-between;
    padding: 1em;
    margin: 0;

    z-index: 10;

    background: linear-gradient(180deg, #2C2546, rgba(0, 0, 0, 0));
  }

  #navigation * {
    margin: 0;
    padding: 0;

    font-size: 2em;

    text-decoration: none;
    color: aliceblue;
    z-index: 5;
    
  }

  #navigation a:hover {
    text-decoration: underline !important;
  }

  #navigation button {
    padding: 0 0.25em;
    margin: 0;

    background: none;
    border: none;

    font-family: 'CutePixel';
    transition: cubic-bezier(0.19, 1, 0.22, 1) 500ms;
  }

  #navigation .menu {
    position: absolute;
    display: flex; 
    flex-direction: column;
    right: 0;
    top: 100%;

    padding: 0em 1em;

    height: fit-content;

    font-size: 1em;

    text-align: right;

    transition: cubic-bezier(0.19, 1, 0.22, 1) 500ms;
  }
</style>