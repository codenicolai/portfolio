<script>
import { base } from "$app/paths";
import Seo from "$lib/components/Seo.svelte";
</script>

<Seo
  title="I ported a Windows game to Mac using Claude"
  description="How Leonardo Nicolai paired with Claude to build a launcher abstraction that got a Windows-only Java game running natively on macOS."
  path="/thoughts/game-mac-port"
  type="article"
/>

<main class="detail-container">
  <a href="{base}/thoughts" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>

  <span class="post-tag">AI · Mac</span>
  <h1 class="post-title">I ported a Windows game to Mac using Claude</h1>
  <p class="post-date">August 21, 2026</p>

  <p class="post-body">Brasfoot, a lightweight Java-based Brazilian football manager game, only ever ran on Windows. It looks for Java through Windows-specific paths, which tools like GPTK and Crossover couldn't fake. So I paired with Claude to build a small abstraction layer that launches it properly on Mac.</p>
  <p class="post-body">We worked through error logs together, iterating on the launcher until the game booted. Took about an hour, and it was a good reminder that AI pair programming is useful well beyond typical web app work.</p>
  <p class="post-body"><a href="https://www.tabnews.com.br/nicolaileo/fiz-um-port-do-brasfoot-para-mac-usando-o-claude" target="_blank" rel="noopener noreferrer" class="post-link">Read the original post →</a></p>
</main>

<style>
.detail-container {
  width: 40vw;
  margin: 2rem auto 5rem auto;
  display: flex;
  flex-direction: column;
  gap: 1.15rem;
}
@media (max-width: 768px) { .detail-container { width: 88vw; } }

.back-link { display: inline-flex; align-items: center; gap: 0.4rem; font-family: "Montserrat", sans-serif; font-size: 0.82rem; font-weight: 600; color: var(--color-text-muted); text-decoration: none; padding: 0.38rem 0.85rem 0.38rem 0.6rem; border-radius: 999px; border: 1px solid var(--color-border); background: transparent; transition: color 0.2s, border-color 0.2s, background 0.2s; margin-bottom: 0.5rem; align-self: flex-start; }
.back-link:hover {
  color: var(--color-text);
  border-color: var(--color-border);
  background: var(--color-tag-bg);
}
.back-icon { width: 12px; height: 12px; fill: currentColor; flex-shrink: 0; }

.post-tag {
  font-family: "Montserrat", sans-serif;
  font-size: 0.7rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--color-sapphire);
}

.post-title {
  font-family: "Montserrat", sans-serif;
  font-size: 1.9rem;
  font-weight: 700;
  margin: 0;
  line-height: 1.3;
  color: var(--color-text);
}

.post-date {
  font-family: "Montserrat", sans-serif;
  font-size: 0.8rem;
  color: var(--color-text-muted);
  margin: -0.4rem 0 0.8rem 0;
}

.post-body {
  font-family: "Montserrat", sans-serif;
  font-size: 0.97rem;
  color: var(--color-text-secondary);
  line-height: 1.85;
  margin: 0;
}

.post-link {
  color: var(--color-sapphire);
  font-weight: 600;
  text-decoration: none;
}
.post-link:hover {
  text-decoration: underline;
}
</style>
