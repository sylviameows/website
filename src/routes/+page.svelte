<script lang="ts">
  import { goto } from '$app/navigation';
  import Container from '$lib/components/Container.svelte';
  import Parallax from '$lib/components/Parallax.svelte';


  function sendTo(url: string) {
    goto(url)
  }
</script>

<Parallax>
  <Container>
    <h1>About Me</h1>
    <p>
      Hai! I'm <span>sylviameows</span>, also known by Vae. 
      My main passion is programming, where I mainly work on random little side-projects.
      Most of my experience is in <span>Minecraft Server/Plugin</span> development with some miscellaneous experience in <span>modding</span>, <span>discord bot development</span>, and more!
    </p>

    <br>

    <h1>Socials</h1>
    <p>
      I'm not found on a lot of places, but here are a few spots you may see me!
    </p>
    <ul class="socials">
      <li><a href="https://github.com/sylviameows">GitHub</a></li>
      <li><a href="https://bsky.sylviameo.ws/profile">Bluesky</a></li>
      <li><a href="https://discord.gg/EvKY9QFDn5">Discord</a></li>
      <li><a href="https://www.youtube.com/@sylviameows">YouTube</a></li>
    </ul>
  </Container>
</Parallax>


<style>

  @media only screen and (max-width: 700px) {
    .socials {
      display: flex;
      flex-direction: column;
      width: 100%;
    
      justify-content: space-around;
      padding-left: 0;

      list-style-type: none;
    }

  }

  .socials {
    display: flex;
    width: 100%;
  
    justify-content: space-around;
    padding-left: 0;

    list-style-type: none;
  }

  .socials li {
    font-size: 2em;
    border: 2px solid aliceblue;
    margin: 0.25em;
    transition: tranform 250ms cubic-bezier(0.19, 1, 0.22, 1);
  }

  .socials li:hover {
    transform: scale(1.1);
  }

  .socials li a {
    display: block;
    padding: 0.25em 0.5em;

    color: aliceblue;
    text-decoration: none;
  }

  h1 {
    font-size: 3em;
    display: inline;
  }

  h1::after {
    content: " ";
    display: block;
    width: 50%;
    position: relative;
    border: 2px solid aliceblue;
  }

  p {
    font-size: 1.5em;
  }

  span {
    color: beige;
  }
</style>