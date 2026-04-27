<main class="detail-container">
  <a href="/thoughts" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>

  <span class="post-tag">React</span>
  <h1 class="post-title">The hidden cost of barrel files</h1>
  <p class="post-date">January 14, 2026</p>

  <p class="post-body">Barrel files — those <code>index.ts</code> files that re-export everything from a folder — feel like a convenience. One import instead of five, paths that read cleanly, no hunting through the filesystem. But what looks like organization often becomes a bundling problem in disguise.</p>
  <p class="post-body">The issue is that bundlers have to parse the entire barrel to determine what's actually used. Even with tree-shaking, circular dependencies can form silently, and in large codebases, import chains grow deep. The result: slower cold starts, larger initial bundles, and module evaluation happening earlier than needed. I've seen build times spike noticeably after a team standardized on barrels without thinking about the consequences.</p>
  <p class="post-body">A concrete example: working on a mid-size dashboard with several feature-heavy modules, I opened Chrome's Network tab during a cold page load and counted over 1,600 module requests. Not all of them were barrel-caused, but after auditing the import chains and switching to direct imports across the feature folders — keeping barrels only at the design system boundary — requests settled between 900 and 1,100 depending on the route. Vite's build time dropped too, a few seconds shaved off a CI step that was already too slow. The change was unglamorous. Nobody noticed. That's how good infrastructure work tends to feel.</p>
  <p class="post-body">The practical advice is simple: favor direct imports for anything performance-sensitive, and reserve barrels for genuine public APIs — the surface of a library or a shared design system, not every subfolder of a feature. A small discipline that pays off quietly over time.</p>
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
