<script lang="ts">
import favicon from "$lib/assets/favicon.svg";
let { children } = $props();
</script>

<style>
  @import "../app.css";

  :global(body) {
    background-color: #f8f8f8; /* Off-white background */
    color: #333; /* Darker text for contrast */
    font-family: Arial, sans-serif;
    font-size: 14px; /* Smaller text */
    line-height: 1.6;
    margin: 0;
    padding: 0;
  }

 

</style>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children()}
