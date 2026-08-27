<script>
import { base } from "$app/paths";
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

  <p class="post-body">There's a phase every React developer goes through where <code>useMemo</code> and <code>useCallback</code> show up on basically everything. I went through it too. It feels responsible, like you're being careful with performance. Nobody tells you memoization has its own cost: more memory, more code to read, dependency arrays you now have to keep correct forever.</p>
  <p class="post-body">I had a filter panel once, a dozen checkboxes and a search box, wrapped top to bottom in <code>useCallback</code> and <code>useMemo</code>. Looked very thorough. Then I actually opened the Profiler and watched it: two re-renders per interaction, under a millisecond each. We were paying for memoization on a component that had never had a performance problem in its life. Ripped it out, lost about 30 lines of dependency arrays, and the code was suddenly readable again. Memoization isn't the villain here. Not measuring first is.</p>
  <p class="post-body">The question I ask now is just: is this actually expensive? Primitive comparisons, cheap. Creating an object, cheap. What's expensive is re-rendering a big tree, or recalculating something across hundreds of items on every keystroke. If you can't point to the problem, you probably don't have one yet.</p>
  <p class="post-body">With the React Compiler stable in 19, most of this manual work is going away anyway, which honestly is a relief. The useful skill going forward isn't memoizing out of habit, it's knowing the few spots where the compiler still needs a hand.</p>
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
  color: var(--color-ruby);
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
