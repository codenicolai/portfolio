<script lang="ts">
import favicon from "$lib/assets/favicon.png";
import avatar from "$lib/assets/avatar.png";
import { base } from "$app/paths";
import { onMount } from "svelte";

let { children } = $props();
let isDark = $state(false);
let flipCount = $state(0);

onMount(() => {
	const saved = localStorage.getItem("theme");
	isDark = saved
		? saved === "dark"
		: window.matchMedia("(prefers-color-scheme: dark)").matches;
	apply();
});

function toggle() {
	isDark = !isDark;
	flipCount += 1;
	localStorage.setItem("theme", isDark ? "dark" : "light");
	apply();
}

function apply() {
	document.documentElement.setAttribute(
		"data-theme",
		isDark ? "dark" : "light",
	);
	const meta = document.querySelector('meta[name="theme-color"]');
	if (meta) meta.setAttribute("content", isDark ? "#404b54" : "#f8f8f8");
}
</script>

<svelte:head>
  <link rel="icon" type="image/png" href={favicon} />
</svelte:head>

<nav class="navbar">
  <button class="theme-toggle" onclick={toggle} aria-label="Toggle theme">
    <span class="icon-coin" style="transform: rotateY({flipCount * 180}deg)">
      {#if isDark}
        <!-- Sun -->
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <circle cx="12" cy="12" r="5"/>
          <line x1="12" y1="1" x2="12" y2="3"/>
          <line x1="12" y1="21" x2="12" y2="23"/>
          <line x1="4.22" y1="4.22" x2="5.64" y2="5.64"/>
          <line x1="18.36" y1="18.36" x2="19.78" y2="19.78"/>
          <line x1="1" y1="12" x2="3" y2="12"/>
          <line x1="21" y1="12" x2="23" y2="12"/>
          <line x1="4.22" y1="19.78" x2="5.64" y2="18.36"/>
          <line x1="18.36" y1="5.64" x2="19.78" y2="4.22"/>
        </svg>
      {:else}
        <!-- Moon -->
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/>
        </svg>
      {/if}
    </span>
  </button>
  <a class="navbar-avatar" href="{base}/contact-me" title="Contact me">
    <img src={avatar} alt="Avatar" />
  </a>
</nav>

{@render children()}

<footer class="footer">© 2022 Leonardo Nicolai</footer>

<style>
  @import "../app.css";

  :global(html) {
    background-color: var(--color-bg);
    transition: background-color 0.25s ease;
  }

  :global(body) {
    background-color: var(--color-bg);
    color: var(--color-text);
    font-family: "Montserrat", sans-serif;
    font-size: 14px;
    line-height: 1.6;
    margin: 0;
    padding: 0;
  }

  .navbar {
    width: 100%;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    gap: 0.75rem;
    padding: 1rem 2rem 0 2rem;
    box-sizing: border-box;
  }

  .navbar-avatar {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--color-avatar-bg);
    box-shadow: 0 2px 8px var(--color-shadow);
    cursor: pointer;
    text-decoration: none;
    flex-shrink: 0;
  }

  .navbar-avatar img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 50%;
    display: block;
  }

  .theme-toggle {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    border: 1px solid var(--color-border);
    background: var(--color-toggle-bg);
    color: var(--color-text-muted);
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: background 0.2s, color 0.2s, border-color 0.2s;
    padding: 0;
    flex-shrink: 0;
    perspective: 200px;
  }

  .theme-toggle:hover {
    background: var(--color-toggle-hover);
    color: var(--color-text);
  }

  .icon-coin {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 16px;
    height: 16px;
    transition: transform 0.5s cubic-bezier(0.65, 0.05, 0.36, 1);
    transform-style: preserve-3d;
  }

  .icon-coin svg {
    width: 16px;
    height: 16px;
  }

  .footer {
    width: 100%;
    box-sizing: border-box;
    padding: 2rem 2rem 1.5rem 2rem;
    text-align: center;
    font-family: "Montserrat", sans-serif;
    font-size: 0.78rem;
    color: var(--color-text-muted);
  }
</style>
