<script>
  import { base } from '$app/paths';
</script>

<main class="detail-container">
  <a href="{base}/" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>
  <h1 class="detail-title">Posts and Thoughts</h1>
  <div class="detail-layout">
    <div class="detail-image">
      <img src="https://images.unsplash.com/photo-1455390582262-044cdead277a?w=700&q=80" alt="Posts and Thoughts" />
    </div>
    <div class="detail-content">
      <p>A space for raw ideas, half-baked theories, and things I've been thinking about lately. Formats over apps — I believe in writing that outlasts the tools used to create it.</p>
      <p>Here you'll find notes on software, design, productivity, and whatever else catches my attention. No strict editorial calendar, just honest writing.</p>
    </div>
  </div>
</main>

<style>
.detail-container { width: 40vw; margin: 2rem auto 4rem auto; display: flex; flex-direction: column; }
@media (max-width: 768px) { .detail-container { width: 88vw; } .detail-layout { flex-direction: column; } .detail-image img { width: 100%; height: 220px; } }
.back-link { display: inline-flex; align-items: center; gap: 0.4rem; font-family: "Montserrat", sans-serif; font-size: 0.82rem; font-weight: 600; color: var(--color-text-muted); text-decoration: none; padding: 0.38rem 0.85rem 0.38rem 0.6rem; border-radius: 999px; border: 1px solid var(--color-border); background: transparent; transition: color 0.2s, border-color 0.2s, background 0.2s; margin-bottom: 1.5rem; align-self: flex-start; }
.back-link:hover {
  color: var(--color-text);
  border-color: var(--color-border);
  background: var(--color-tag-bg);
}
.back-icon { width: 12px; height: 12px; fill: currentColor; flex-shrink: 0; }
.detail-title { font-family: "Montserrat", sans-serif; font-size: 2rem; font-weight: 700; margin: 0 0 2rem 0; color: var(--color-text); }
.detail-layout { display: flex; gap: 2.5rem; align-items: flex-start; }
.detail-image { flex: 0 0 45%; }
.detail-image img { width: 100%; height: 320px; object-fit: cover; border-radius: 14px; display: block; box-shadow: 0 4px 24px var(--color-img-shadow); }
.detail-content { flex: 1; display: flex; flex-direction: column; gap: 1rem; }
.detail-content p { font-family: "Montserrat", sans-serif; font-size: 1rem; color: var(--color-text-secondary); line-height: 1.75; margin: 0; }
</style>
