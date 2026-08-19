<script>
import { base } from "$app/paths";
</script>

<main class="detail-container">
  <a href="{base}/" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>
  <div class="title-row">
    <h1 class="detail-title">Contact me</h1>
    <a
      class="resume-btn"
      href="{base}/Leonardo_Nicolai_Resume.pdf"
      download="Leonardo_Nicolai_Resume.pdf"
      aria-label="Download resume"
      title="Download resume"
    >
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
        <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4" />
        <polyline points="7 10 12 15 17 10" />
        <line x1="12" y1="15" x2="12" y2="3" />
      </svg>
    </a>
  </div>
  <div class="detail-layout">
    <div class="detail-image">
        <img src="{base}/github_photo.png" alt="Contact me" />
    </div>
    <div class="detail-content">
      <p>Fullstack engineer with 7+ years shipping products end to end. React on the front, Node, Express, and Prisma on the back. These days I lead a team of six as a technical lead, and I've spent enough time wiring AI into real products to know where it actually helps and where it's just noise.</p>
      <p>If something on this site resonated or if you're working on something interesting. I'm easy to reach.</p>
      <a href="https://github.com/codenicolai" class="contact-link" target="_blank" rel="noopener noreferrer">
        <svg class="contact-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <path d="M471.1 297.4C483.6 309.9 483.6 330.2 471.1 342.7L279.1 534.7C266.6 547.2 246.3 547.2 233.8 534.7C221.3 522.2 221.3 501.9 233.8 489.4L403.2 320L233.9 150.6C221.4 138.1 221.4 117.8 233.9 105.3C246.4 92.8 266.7 92.8 279.2 105.3L471.2 297.3z"/>
        </svg>
        github.com/codenicolai
      </a>
      <a href="https://www.linkedin.com/in/nicolaileonardo/" class="contact-link" target="_blank" rel="noopener noreferrer">
        <svg class="contact-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <path d="M471.1 297.4C483.6 309.9 483.6 330.2 471.1 342.7L279.1 534.7C266.6 547.2 246.3 547.2 233.8 534.7C221.3 522.2 221.3 501.9 233.8 489.4L403.2 320L233.9 150.6C221.4 138.1 221.4 117.8 233.9 105.3C246.4 92.8 266.7 92.8 279.2 105.3L471.2 297.3z"/>
        </svg>
        linkedin.com/in/nicolaileonardo
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
      <div class="contact-line">GMT-3 · Florianópolis, Brazil</div>
    </div>
  </div>
</main>

<style>
.detail-container { width: 40vw; margin: 2rem auto 4rem auto; display: flex; flex-direction: column; }
@media (max-width: 768px) { .detail-container { width: 88vw; } .detail-image img { height: 220px; } }
.back-link { display: inline-flex; align-items: center; gap: 0.4rem; font-family: "Montserrat", sans-serif; font-size: 0.82rem; font-weight: 600; color: var(--color-text-muted); text-decoration: none; padding: 0.38rem 0.85rem 0.38rem 0.6rem; border-radius: 999px; border: 1px solid var(--color-border); background: transparent; transition: color 0.2s, border-color 0.2s, background 0.2s; margin-bottom: 1.5rem; align-self: flex-start; }
.back-link:hover {
  color: var(--color-text);
  border-color: var(--color-border);
  background: var(--color-tag-bg);
}
.back-icon { width: 12px; height: 12px; fill: currentColor; flex-shrink: 0; }
.title-row { display: flex; align-items: center; justify-content: space-between; gap: 1rem; margin: 0 0 2rem 0; }
.detail-title { font-family: "Montserrat", sans-serif; font-size: 2rem; font-weight: 700; margin: 0; color: var(--color-text); }
.resume-btn {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: 1px solid var(--color-border);
  background: var(--color-toggle-bg);
  color: var(--color-text-muted);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background 0.2s, color 0.2s, border-color 0.2s;
  flex-shrink: 0;
}
.resume-btn:hover {
  background: var(--color-toggle-hover);
  color: var(--color-text);
}
.resume-btn svg {
  width: 16px;
  height: 16px;
}
.detail-layout { display: flex; flex-direction: column; gap: 1.5rem; }
.detail-image { width: 100%; }
.detail-image img { width: 100%; height: 320px; object-fit: cover; border-radius: 14px; display: block; box-shadow: 0 4px 24px var(--color-img-shadow); }
.detail-content { flex: 1; display: flex; flex-direction: column; gap: 1rem; }
.detail-content p { font-family: "Montserrat", sans-serif; font-size: 1rem; color: var(--color-text-secondary); line-height: 1.75; margin: 0; }
.contact-link { display: inline-flex; align-items: center; gap: 0.45rem; font-family: "Montserrat", sans-serif; font-size: 0.95rem; font-weight: 600; color: var(--color-text); text-decoration: none; transition: opacity 0.2s; }
.contact-link:hover { opacity: 0.75; text-decoration: underline; }
.contact-icon { width: 11px; height: 11px; fill: currentColor; flex-shrink: 0; }
.contact-line { font-family: "Montserrat", sans-serif; font-size: 0.85rem; font-weight: 600; color: var(--color-text-muted); margin-left: calc(11px + 0.45rem); }
</style>
