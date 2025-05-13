<script>
  import Parallax from "$lib/components/Parallax.svelte";

  import { page } from '$app/state'
  import Container from "$lib/components/Container.svelte";

</script>

<div class="error">
  <div>
    <h1 class="error">{page.status}</h1>
    <p class="error">{page.error?.message}</p>
  </div>
</div>


<Parallax>
  <Container>
    <h1>Sorry we had an issue loading this page, if you believe this is an error report it in the <a href="https://discord.gg/EvKY9QFDn5" target="_blank" rel="noopener noreferrer">Discord</a>!</h1>
  </Container>
</Parallax>

<style>
  h1.error {
    font-size: 5em;
    text-align: center;
  }

  p.error {
    font-size: 2em;
    text-align: center;
  }

  div.error {
    z-index: -1;
    display: flex;
    position: absolute;
    width: 100vw;
    height: 100vh;

    background: radial-gradient(#2C2546, rgba(0,0,0,0) 25%);
  }

  div.error * {
    margin: auto;
  }

  a {
    color: beige
  }
</style>