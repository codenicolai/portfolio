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

  <span class="post-tag">React</span>
  <h1 class="post-title">Memoization in React: when it helps and when it just adds noise</h1>
  <p class="post-date">October 30, 2025</p>

  <p class="post-body">There's a phase most React developers go through where they start wrapping everything in <code>useMemo</code> and <code>useCallback</code>. It feels responsible — caching things, preventing re-renders, being thoughtful about performance. But memoization has a cost too: memory, code complexity, and the cognitive overhead of tracking dependencies correctly.</p>
  <p class="post-body">At one point we had a filter panel component — a dozen checkboxes and a search input — where every handler was wrapped in <code>useCallback</code> and every derived value in <code>useMemo</code>. It looked thorough. When I profiled it with React DevTools Profiler, the component was re-rendering maybe twice per interaction and each render took under 1ms. We were paying the memoization overhead for a component that had no performance problem to begin with. Removing it cut about 30 lines of dependency arrays and made the code straightforward to read again. The lesson wasn't that memoization is bad — it's that measuring first changes everything.</p>
  <p class="post-body">The real question is whether the computation or reference is actually expensive. Primitive comparisons are cheap. Object creation is cheap. What's expensive is re-rendering a complex tree, or recalculating something that touches hundreds of items on every keystroke. Memoization makes sense when you can measure the problem it solves — not as a default style.</p>
  <p class="post-body">With the React Compiler now stable in React 19, a lot of manual memoization will become unnecessary — the compiler handles referential stability automatically. The best thing you can do now is understand the primitives well enough to recognize where the compiler still needs your help.</p>
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
