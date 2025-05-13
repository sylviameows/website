<script lang="ts">
  let { children } = $props();
</script>

<div class="holder">
  <div class="container">
    {@render children()}
  </div>
</div>

<style>
  .holder {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;

   
  }

  .container {
    width: 100%;
    max-width: min(calc(100% - 2em), 700px);
    padding: 0 1em;
  }
</style>