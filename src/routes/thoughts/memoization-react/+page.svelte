<script>
import { base } from "$app/paths";
import Seo from "$lib/components/Seo.svelte";
</script>

<Seo
  title="Memoization in React: when it helps and when it just adds noise"
  description="useMemo and useCallback everywhere isn't a performance strategy. Notes on measuring first, and what the React Compiler changes."
  path="/thoughts/memoization-react"
  type="article"
/>

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

  <p class="post-body">There's a phase every React developer goes through where <code>useMemo</code> and <code>useCallback</code> end up on basically everything. I went through it too, hard. It feels responsible, like proof you actually cared about performance. Nobody tells you upfront that memoization isn't free, it costs memory, it costs readability, and it leaves you babysitting dependency arrays for the rest of that component's life.</p>
  <p class="post-body">I had a filter panel once. A dozen checkboxes, a search box, wrapped top to bottom in <code>useCallback</code> and <code>useMemo</code> like a security blanket. Looked very responsible on paper. Then I actually opened the <a class="post-link" href="https://react.dev/learn/react-developer-tools" target="_blank" rel="noopener noreferrer">React Profiler</a> and watched what was really happening: two re-renders per interaction, under a millisecond each. I was protecting a component from a performance problem it never had in its life. Ripped all of it out, deleted about thirty lines of dependency arrays, and the file was suddenly readable again for the first time in months.</p>
  <p class="post-body">Because that's really the whole point of memoization, and it took me embarrassingly long to say out loud: you're telling React "you already did this work, don't do it again unless something actually changed." That's the entire deal. It's not a performance ritual you perform to look careful, it's a note about work that doesn't need repeating. If the work was never expensive to begin with, that note is pure overhead, you're paying to remember something nobody needed remembered.</p>
  <p class="post-body">So the question I actually ask now is just: is this expensive enough that redoing it matters? Comparing primitives, cheap, do it a thousand times a second and nobody notices. Creating a plain object, cheap. What's expensive is re-rendering a heavy tree, or recalculating something across hundreds of rows on every keystroke. If you can't point at the actual work being repeated, you don't have a case for memoizing it yet, you just have a feeling.</p>
  <p class="post-body">With the React Compiler stable in 19, most of this manual bookkeeping is quietly going away, and honestly, good riddance. The skill that matters going forward isn't reaching for <code>useMemo</code> out of habit, it's still knowing how to open the Profiler, see what's actually re-running, and recognize the handful of spots where the compiler still needs a human to point at the real work.</p>
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

code {
  font-family: "Courier New", monospace;
  font-size: 0.88em;
  background: var(--color-tag-bg);
  color: var(--color-tag-text);
  padding: 0.1em 0.4em;
  border-radius: 4px;
}
</style>
