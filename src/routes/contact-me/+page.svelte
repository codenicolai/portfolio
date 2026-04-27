<main class="detail-container">
  <a href="/" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>
  <h1 class="detail-title">Contact me</h1>
  <p class="detail-date">October 2, 2025</p>
  <div class="detail-layout">
    <div class="detail-image">
        <img src="/github_photo.png" alt="Contact me" />
    </div>
    <div class="detail-content">
      <p>Frontend engineer with 7+ years building products people actually use. I work mostly in React, care a lot about performance and good UI, and have been integrating AI tools into real workflows long enough to know when it helps and when it's just hype.</p>
      <p>If something on this site resonated — or if you're working on something interesting — I'm easy to reach.</p>
      <a href="https://github.com/codenicolai" class="contact-link" target="_blank" rel="noopener noreferrer">
        <svg class="contact-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <path d="M471.1 297.4C483.6 309.9 483.6 330.2 471.1 342.7L279.1 534.7C266.6 547.2 246.3 547.2 233.8 534.7C221.3 522.2 221.3 501.9 233.8 489.4L403.2 320L233.9 150.6C221.4 138.1 221.4 117.8 233.9 105.3C246.4 92.8 266.7 92.8 279.2 105.3L471.2 297.3z"/>
        </svg>
        github.com/codenicolai
      </a>
      <a href="mailto:nicolaileo@outlook.com" class="contact-link">
        <svg class="contact-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <path d="M471.1 297.4C483.6 309.9 483.6 330.2 471.1 342.7L279.1 534.7C266.6 547.2 246.3 547.2 233.8 534.7C221.3 522.2 221.3 501.9 233.8 489.4L403.2 320L233.9 150.6C221.4 138.1 221.4 117.8 233.9 105.3C246.4 92.8 266.7 92.8 279.2 105.3L471.2 297.3z"/>
        </svg>
        nicolaileo@outlook.com
      </a>
      <a href="tel:+5546999423353" class="contact-link">
        <svg class="contact-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <path d="M471.1 297.4C483.6 309.9 483.6 330.2 471.1 342.7L279.1 534.7C266.6 547.2 246.3 547.2 233.8 534.7C221.3 522.2 221.3 501.9 233.8 489.4L403.2 320L233.9 150.6C221.4 138.1 221.4 117.8 233.9 105.3C246.4 92.8 266.7 92.8 279.2 105.3L471.2 297.3z"/>
        </svg>
        +55 (46) 99942-3353
      </a>
    </div>
  </div>
</main>

<style>
.detail-container { width: 60vw; margin: 2rem auto 4rem auto; display: flex; flex-direction: column; }
@media (max-width: 768px) { .detail-container { width: 88vw; } .detail-layout { flex-direction: column; } .detail-image img { width: 100%; height: 220px; } }
.back-link { display: inline-flex; align-items: center; gap: 0.4rem; font-family: "Montserrat", sans-serif; font-size: 0.82rem; font-weight: 600; color: var(--color-text-muted); text-decoration: none; padding: 0.38rem 0.85rem 0.38rem 0.6rem; border-radius: 999px; border: 1px solid var(--color-border); background: transparent; transition: color 0.2s, border-color 0.2s, background 0.2s; margin-bottom: 1.5rem; align-self: flex-start; }
.back-link:hover { color: var(--color-accent); border-color: var(--color-accent); background: var(--color-accent-subtle); }
.back-icon { width: 12px; height: 12px; fill: currentColor; flex-shrink: 0; }
.detail-title { font-family: "Montserrat", sans-serif; font-size: 2rem; font-weight: 700; margin: 0 0 0.3rem 0; background: linear-gradient(90deg, var(--color-accent) 0%, var(--color-accent-to) 60%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; color: transparent; }
.detail-date { font-family: "Montserrat", sans-serif; font-size: 0.9rem; color: var(--color-text-muted); margin: 0 0 2rem 0; }
.detail-layout { display: flex; gap: 2.5rem; align-items: flex-start; }
.detail-image { flex: 0 0 45%; }
.detail-image img { width: 100%; height: 320px; object-fit: cover; border-radius: 14px; display: block; box-shadow: 0 4px 24px var(--color-img-shadow); }
.detail-content { flex: 1; display: flex; flex-direction: column; gap: 1rem; }
.detail-content p { font-family: "Montserrat", sans-serif; font-size: 1rem; color: var(--color-text-secondary); line-height: 1.75; margin: 0; }
.contact-link { display: inline-flex; align-items: center; gap: 0.45rem; font-family: "Montserrat", sans-serif; font-size: 0.95rem; font-weight: 600; color: var(--color-accent); text-decoration: none; transition: opacity 0.2s; }
.contact-link:hover { opacity: 0.75; text-decoration: underline; }
.contact-icon { width: 11px; height: 11px; fill: currentColor; flex-shrink: 0; }
</style>
