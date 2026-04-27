<main class="detail-container">
  <a href="/" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>

  <h1 class="detail-title">Thoughts</h1>
  <p class="detail-subtitle">Notes on tech, React, and the job.</p>

  <a href="/thoughts/tech-lead" class="post-item">
    <span class="post-tag">Leadership</span>
    <h2 class="post-title">Becoming a tech lead when you were just writing code</h2>
    <p class="post-date">April 2, 2026</p>
  </a>

  <div class="divider"></div>

  <a href="/thoughts/barrel-files" class="post-item">
    <span class="post-tag">React</span>
    <h2 class="post-title">The hidden cost of barrel files</h2>
    <p class="post-date">January 14, 2026</p>
  </a>

  <div class="divider"></div>

  <a href="/thoughts/memoization-react" class="post-item">
    <span class="post-tag">React</span>
    <h2 class="post-title">Memoization in React: when it helps and when it just adds noise</h2>
    <p class="post-date">October 30, 2025</p>
  </a>

  <div class="divider"></div>

  <a href="/thoughts/react-news" class="post-item">
    <span class="post-tag">React · News</span>
    <h2 class="post-title">What's actually changed in React lately</h2>
    <p class="post-date">March 18, 2025</p>
  </a>
</main>

<style>
.detail-container {
  width: 52vw;
  margin: 2rem auto 5rem auto;
  display: flex;
  flex-direction: column;
}
@media (max-width: 900px) { .detail-container { width: 88vw; } }

.back-link { display: inline-flex; align-items: center; gap: 0.4rem; font-family: "Montserrat", sans-serif; font-size: 0.82rem; font-weight: 600; color: var(--color-text-muted); text-decoration: none; padding: 0.38rem 0.85rem 0.38rem 0.6rem; border-radius: 999px; border: 1px solid var(--color-border); background: transparent; transition: color 0.2s, border-color 0.2s, background 0.2s; margin-bottom: 1.5rem; align-self: flex-start; }
.back-link:hover { color: var(--color-accent); border-color: var(--color-accent); background: var(--color-accent-subtle); }
.back-icon { width: 12px; height: 12px; fill: currentColor; flex-shrink: 0; }

.detail-title {
  font-family: "Montserrat", sans-serif;
  font-size: 2rem;
  font-weight: 700;
  margin: 0 0 0.3rem 0;
  background: linear-gradient(90deg, var(--color-accent) 0%, var(--color-accent-to) 60%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  color: transparent;
}
.detail-subtitle {
  font-family: "Montserrat", sans-serif;
  font-size: 0.9rem;
  color: var(--color-text-muted);
  margin: 0 0 3rem 0;
}

.post-item {
  display: flex;
  flex-direction: column;
  gap: 0.45rem;
  padding: 0.5rem 0.25rem;
  text-decoration: none;
  transition: transform 0.38s cubic-bezier(0.22, 0.61, 0.36, 1);
  will-change: transform;
}
.post-item:hover {
  transform: scale(1.01);
  cursor: pointer;
}
.post-item:hover .post-title {
  text-decoration: underline;
}

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
  font-size: 1.25rem;
  font-weight: 700;
  color: var(--color-text-secondary);
  margin: 0;
  line-height: 1.4;
}

.post-date {
  font-family: "Montserrat", sans-serif;
  font-size: 0.8rem;
  color: var(--color-text-muted);
  margin: 0;
}

.divider {
  width: 100%;
  height: 1px;
  background: var(--color-border);
  margin: 1.5rem 0;
}
</style>
