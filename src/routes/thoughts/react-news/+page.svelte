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

  <p class="post-body">React 19 landed with more substance than most major versions. The two things I care most about: the React Compiler finally shipping, and the <code>use()</code> hook. The compiler eliminates the manual memoization tax — no more <code>useCallback</code> everywhere just to stabilize references. <code>use()</code> lets you read a Promise or context inside any component, not just at the top level, which unlocks cleaner async patterns without waterfall suspense trees.</p>
  <p class="post-body">When we migrated some data-fetching flows from the classic <code>useEffect</code> + <code>useState</code> pattern to Suspense-based fetching with <code>use()</code>, the difference showed up in traces. A settings page that was making three sequential requests — each waiting on the previous — dropped from around 900ms to roughly 350ms once the fetches ran in parallel and Suspense boundaries handled the loading states. It's not magic; the new primitives just make it easier to express the right behavior without fighting the framework.</p>
  <p class="post-body"><code>useTransition</code> has been around since React 18 but it's become more central to how I think about UI responsiveness. Marking state updates as non-urgent so the UI stays interactive during heavy renders is exactly the kind of primitive that makes the framework feel thoughtful. Combine it with <code>useDeferredValue</code> and you have solid tools for perceived performance without reaching for external libraries.</p>
  <p class="post-body">Server Components are the shift that's still settling. The mental model of a component tree split between server and client is powerful but genuinely different from what most of us have built for years. It's not a drop-in upgrade — it's a rethink of where data fetching lives. I'm cautiously optimistic, especially as Next.js makes the boundaries cleaner to work with.</p>
</main>

<style>
.detail-container {
  width: 52vw;
  margin: 2rem auto 5rem auto;
  display: flex;
  flex-direction: column;
  gap: 1.15rem;
}
@media (max-width: 900px) { .detail-container { width: 88vw; } }

.back-link { display: inline-flex; align-items: center; gap: 0.4rem; font-family: "Montserrat", sans-serif; font-size: 0.82rem; font-weight: 600; color: var(--color-text-muted); text-decoration: none; padding: 0.38rem 0.85rem 0.38rem 0.6rem; border-radius: 999px; border: 1px solid var(--color-border); background: transparent; transition: color 0.2s, border-color 0.2s, background 0.2s; margin-bottom: 0.5rem; align-self: flex-start; }
.back-link:hover { color: var(--color-accent); border-color: var(--color-accent); background: var(--color-accent-subtle); }
.back-icon { width: 12px; height: 12px; fill: currentColor; flex-shrink: 0; }

.post-tag {
  font-family: "Montserrat", sans-serif;
  font-size: 0.7rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--color-accent);
}

.post-title {
  font-family: "Montserrat", sans-serif;
  font-size: 1.9rem;
  font-weight: 700;
  margin: 0;
  line-height: 1.3;
  background: linear-gradient(90deg, var(--color-accent) 0%, var(--color-accent-to) 60%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  color: transparent;
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
