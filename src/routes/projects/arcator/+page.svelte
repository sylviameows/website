<script lang="ts">
  import arcatorSpawn from "$lib/assets/arcator_spawn.png"

  import Container from "$lib/components/Container.svelte";
</script>

<Container>
  <br style="margin-top: 3em;">
  <div>
    <img class="hero_image" src={arcatorSpawn} alt="arcator hub's spawn region">
  </div>
  <h1>Arcator Network</h1>
  <p>
    Arcator is a Minecraft server network that began in late 2010 as the <span style="text-decoration: underline;">first</span> "true freebuild" server. 
    I was introduced to this server in <span>2017</span> and have since became an admin and manage, update, and create servers for the network.
  </p>

  <blockquote cite="https://arcator.co.uk/">
    Here at Arcator, we want to give people the best possible experience they can have. New people can build straight away and make use of the majority of commands. It's frustrating when it takes weeks to become trusted on a server. If you want a place where you can just build and worry about ranks later, Arcator is the place for you.
    <a href="https://arcator.co.uk/">Arcator Network</a>
  </blockquote>

  <p>
    My main contributions to the server include the <span>Minigames</span> and <span>Strawberry SMP (SSMP)</span> servers. Additionally I've contributed a few various modpacks and servers for those modpacks.
  </p>

  <div class="find">
    <p>arcator.co.uk</p>
    <a href="https://discord.com/invite/GwArgw2">Join Discord</a>
  </div>

  <br style="margin-bottom: 3em;">
</Container>

<style>
  .find {
    display: flex;
    width: 100%;
    justify-content: space-between;

  }

  .find * {
    margin: 0;
    padding: 0;

    font-size: 2em;
  }

  .hero_image {
    position: relative;
    width: 120%;
    left: -10%;

    border-radius: 2em;
  }

  blockquote {
    font-size: 1.25em;
    margin-left: 0;
    padding-left: 1em;
    border-left: 4px solid rgba(240, 248, 255, 0.5);
  }

  blockquote a::before {
    content: "- ";
    display: inline;
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

  span,a  {
    color: beige;
  }
</style>