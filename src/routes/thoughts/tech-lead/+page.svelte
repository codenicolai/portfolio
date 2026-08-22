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

  <span class="post-tag">Leadership</span>
  <h1 class="post-title">Becoming a tech lead when you were just writing code</h1>
  <p class="post-date">April 2, 2026</p>

  <p class="post-body">Nobody warns you that the first real skill you need as a lead has nothing to do with architecture. It's estimating work you're not going to do yourself. When I was coding full time, I had a feel for how long things took, in my hands, in my head. Once I had a team, I was estimating for people with different skill levels, in parts of the codebase they didn't know as well as I did. My gut was useless for that. Took me longer than I'd like to admit to notice.</p>
  <p class="post-body">These days I treat every deadline as a first guess, not a promise. It's almost always wrong, and that's fine — what matters is catching it early. Short check-ins, clear scope, and honestly, the harder part: building a team where someone can tell me "I'm stuck, this is going to take longer" without feeling like they messed up. I didn't get that from a process doc. I got it from watching how people reacted the first couple times it happened, mine included.</p>
  <p class="post-body">Trade-offs are basically the job now. Speed vs. safety, consistency vs. whatever the product actually needs this week. I used to always want the cleanest solution. But clean has a schedule cost, and sometimes the right move is the slightly uglier one that ships and doesn't block five other people. Saying "this is good enough for now, we'll revisit it" took practice. I still don't love saying it.</p>
  <p class="post-body">The bigger shift, honestly, was learning to stop fixing things myself. Early on I'd jump in because I could do it faster, and that felt helpful. It wasn't. It just meant people stayed dependent on me and I became the bottleneck. Letting someone do it differently than I would have, and accepting that "different" is usually just fine, that's most of what delegating actually is.</p>
  <p class="post-body">Coming from development helps in obvious ways. I know where the complexity actually hides, I can tell when someone's genuinely stuck versus spinning their wheels. But it also means I sometimes forget that what feels easy to me took me years to feel easy. Now when something isn't landing, I try to ask what would make it clearer instead of assuming it's an effort problem. Small change, better outcome.</p>
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
