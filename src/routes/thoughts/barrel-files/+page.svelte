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
  <h1 class="post-title">The hidden cost of barrel files</h1>
  <p class="post-date">January 14, 2026</p>

  <p class="post-body">I used to love barrel files. Those <code>index.ts</code> files that re-export everything from a folder, so you get one tidy import instead of five. No digging through the filesystem to find the right path. What's not to like? Turns out plenty, once a codebase grows past "small."</p>
  <p class="post-body">The problem is bundlers have to parse the whole barrel to figure out what's actually being used. Tree-shaking helps, but not as much as people assume. Circular dependencies sneak in quietly, import chains get deep, and modules start evaluating way earlier than they need to. I watched a team's build times creep up for weeks before anyone connected it to the barrels they'd standardized on.</p>
  <p class="post-body">On one dashboard project I was debugging, I opened the Network tab on a cold load out of curiosity and counted over 1,600 module requests. Sixteen hundred. Not all of that was barrels, but after I went through and switched the feature folders to direct imports, keeping barrels only around the design system, it settled down to somewhere between 900 and 1,100 depending on the route. Vite's build got a few seconds faster too. Nobody on the team really noticed the change, which is honestly how you know infrastructure work went well.</p>
  <p class="post-body">My rule now: direct imports for anything performance-sensitive, barrels only for things that are genuinely public, a library's surface, a shared design system. Not every folder that happens to have more than one file in it.</p>
</main>

<style>
.detail-container {
  width: 40vw;
  margin: 2rem auto 5rem auto;
  display: flex;
  flex-direction: column;
  gap: 1.15rem;
}
@media (max-width: 900px) { .detail-container { width: 88vw; } }

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
