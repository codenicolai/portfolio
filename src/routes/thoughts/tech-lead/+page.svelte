<main class="detail-container">
  <a href="/thoughts" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>

  <span class="post-tag">Leadership</span>
  <h1 class="post-title">Becoming a tech lead when you were just writing code</h1>
  <p class="post-date">April 2, 2026</p>

  <p class="post-body">The first real challenge of moving into a lead role isn't the architecture decisions or the 1:1s — it's estimating and distributing work. When you're coding, you have a gut feel for how long things take. When you're responsible for a team, you're estimating work you won't be doing yourself, for people at different skill levels, in codebases they know differently than you do. Your gut is the wrong tool.</p>
  <p class="post-body">I've learned to treat deadlines as hypotheses, not commitments. The first estimate is almost always wrong. What matters is building a feedback loop fast enough to catch it early — short cycles, clear scope, honest conversations before the deadline, not after. The hardest part is creating an environment where someone can say "I'm stuck and this will take longer" without it feeling like failure. That culture doesn't come from a process doc; it comes from how you respond the first few times it happens.</p>
  <p class="post-body">Trade-offs are the core of the role. Almost every technical decision is a negotiation between speed and safety, consistency and pragmatism, what the team can maintain and what the product needs right now. The instinct is to always want the cleanest solution — but clean has a schedule cost, and sometimes the right call is a slightly less elegant one that ships on time and doesn't block six other people. Getting comfortable saying "this is good enough for now, and here's when we revisit it" is more useful than holding out for perfect.</p>
  <p class="post-body">The other shift is learning to step back. Early on, I'd jump in and fix things because I could do it faster. That's a trap. The fastest path in the short term is the slowest path for the team — it keeps people dependent, it bottlenecks the work in you, and it prevents others from growing into ownership. Delegating well means trusting that someone will do it differently than you would, and that different is usually fine. Your job stops being to write the best code and starts being to create the conditions where other people can.</p>
  <p class="post-body">Coming from development helps: I know where complexity hides, I can read a PR at the right level, and I understand when someone is blocked on a real problem versus spinning. But it also creates blind spots. Not everything that feels easy to me is easy for someone earlier in their career. The best adjustment I've made is asking "what would make this clearer?" instead of assuming the gap is effort.</p>
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
