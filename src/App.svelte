<script>
  import svelteLogo from "./assets/svelte.svg";
  import Counter from "./lib/Counter.svelte";
  import Map from "./Map.svelte";
  export let ready;
</script>

<svelte:head>
  <script
    defer
    async
    src="https://maps.googleapis.com/maps/api/js?key=AIzaSyC5Zp98lbWecDHTKT1gSCyAv595X-dSyKk&callback=initMap"
  >
  </script>
</svelte:head>

<main>
  <h1>Google Maps + Svelte</h1>

  {#if ready}
    <Map /><div class="card">
      <Counter />
    </div>
  {/if}
  <p class="read-the-docs">Click on the Vite and Svelte logos to learn more</p>
</main>

<style>
  :global(body) {
    padding: 0;
  }
  .read-the-docs {
    color: #888;
  }
</style>