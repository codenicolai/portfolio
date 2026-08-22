<script>
  import { onMount } from 'svelte';

  onMount(() => {
    // Old links pointed to /portfolio/... from when the site was hosted
    // under a GitHub Pages project-page subpath. Strip that prefix and
    // send visitors to the same path at the new root-hosted site.
    const match = window.location.pathname.match(/^\/portfolio(\/.*)?$/);
    if (match) {
      window.location.replace((match[1] || '/') + window.location.search + window.location.hash);
    }
  });
</script>

<main class="not-found">
  <p>Page not found. <a href="/">Go home</a></p>
</main>

<style>
  .not-found {
    min-height: 60vh;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: "Montserrat", sans-serif;
    font-size: 0.9rem;
    color: var(--color-text-muted);
  }
  .not-found a {
    color: var(--color-text);
  }
</style>
