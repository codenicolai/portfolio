<script>
  import { base } from '$app/paths';
</script>

<main class="detail-container">
  <a href="{base}/thoughts" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>

  <span class="post-tag">React · News</span>
  <h1 class="post-title">What's actually changed in React lately</h1>
  <p class="post-date">March 18, 2025</p>

  <p class="post-body">React 19 actually shipped something this time. Two things stuck with me: the compiler finally being real, and <code>use()</code>. The compiler kills most of the reason I was ever writing <code>useCallback</code> everywhere. <code>use()</code> lets you read a promise or context from inside any component, not just at the top, which quietly fixes a bunch of awkward async patterns I'd been working around for years.</p>
  <p class="post-body">We moved a few data-fetching flows off the classic <code>useEffect</code> plus <code>useState</code> combo and onto Suspense with <code>use()</code>. The difference showed up immediately in the traces. A settings page that used to fire three requests one after another, each waiting on the last, went from about 900ms to roughly 350ms once they ran in parallel and Suspense handled the loading states. Nothing clever about it — the new primitives just made the right behavior the easy one to write.</p>
  <p class="post-body"><code>useTransition</code> has been around since 18 but I lean on it a lot more now. Marking an update as non-urgent so the UI doesn't freeze during a heavy render, pair it with <code>useDeferredValue</code>, and you've got real tools for perceived performance without pulling in another library.</p>
  <p class="post-body">Server Components are the part that's still settling for me, if I'm honest. Splitting a component tree across server and client is a genuinely different model from what most of us built for a decade. It's not a drop-in upgrade, it's a rethink of where your data fetching even lives. Cautiously into it, especially now that Next.js has made the boundaries less confusing.</p>
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

code {
  font-family: "Courier New", monospace;
  font-size: 0.88em;
  background: var(--color-tag-bg);
  color: var(--color-tag-text);
  padding: 0.1em 0.4em;
  border-radius: 4px;
}
</style>
