<main class="detail-container">
  <a href="/" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>

  <h1 class="detail-title">Events and Workshops</h1>
  <p class="detail-date">October 21, 2025</p>

  <!-- TDC Innovation 2025 -->
  <section class="event">
    <span class="event-tag">Conference</span>
    <h2 class="event-title">TDC Innovation — Florianópolis</h2>
    <p class="event-date">2025</p>

    <p class="body-text">Attended TDC Innovation in Florianópolis, one of the largest developer conferences in Brazil. The experience was a great opportunity to reconnect with the dev community and exchange ideas with engineers across different stacks and companies.</p>

    <figure class="photo">
      <img src="/TDC_1.JPG" alt="TDC Innovation — talk in progress" />
      <figcaption>Talk in progress at #THEDEVCONF</figcaption>
    </figure>

    <p class="body-text">Highlights included a tech lead track focused on team dynamics, decision-making under pressure, and how to balance technical depth with leadership responsibilities — themes that resonate a lot with my current role at Atlas Governance.</p>
    <p class="body-text">Being in the room with people who are genuinely passionate about the craft is always energizing. The conversations between talks are often more valuable than the talks themselves.</p>

    <figure class="photo">
      <img src="/TDC_2.JPG" alt="TDC Innovation — Premium badge" />
      <figcaption>Leonardo Nicolai  #THEDEVCONF</figcaption>
    </figure>
  </section>
</main>

<style>
.detail-container {
  width: 52vw;
  margin: 2rem auto 4rem auto;
  display: flex;
  flex-direction: column;
}
@media (max-width: 900px) {
  .detail-container { width: 88vw; }
}

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
.detail-date {
  font-family: "Montserrat", sans-serif;
  font-size: 0.9rem;
  color: var(--color-text-muted);
  margin: 0 0 3rem 0;
}

.event {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.event-tag {
  font-family: "Montserrat", sans-serif;
  font-size: 0.72rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--color-accent);
}

.event-title {
  font-family: "Montserrat", sans-serif;
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--color-text-secondary);
  margin: 0;
}

.event-date {
  font-family: "Montserrat", sans-serif;
  font-size: 0.85rem;
  color: var(--color-text-muted);
  margin: -0.75rem 0 0 0;
}

.body-text {
  font-family: "Montserrat", sans-serif;
  font-size: 1rem;
  color: var(--color-text-secondary);
  line-height: 1.8;
  margin: 0;
}

/* Medium-style photo */
.photo {
  margin: 0.5rem 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.6rem;
}

.photo img {
  width: 100%;
  max-height: 480px;
  object-fit: cover;
  border-radius: 10px;
  display: block;
  box-shadow: 0 4px 24px var(--color-img-shadow);
}

.photo figcaption {
  font-family: "Montserrat", sans-serif;
  font-size: 0.78rem;
  color: var(--color-text-muted);
  text-align: center;
}
</style>
