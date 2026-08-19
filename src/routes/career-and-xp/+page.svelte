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

  <h1 class="detail-title">Career &amp; XP</h1>

  <!-- Experience -->
  <section class="section">
    <h2 class="section-title">Experience</h2>

    <div class="timeline">
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-body">
          <div class="timeline-header">
            <span class="company">Atlas Governance</span>
            <span class="role">Technical Lead</span>
            <span class="period">Jun 2022 – Present · Remote</span>
          </div>
          <p class="timeline-desc">Leads a team of 6 developers and QAs on a shareholder-management platform handling datasets of up to 500K shareholders, owning discovery, estimates, and delivery. Delivered 3 AI-powered integrations, translation, transcription, and summarization.</p>
        </div>
      </div>

      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-body">
          <div class="timeline-header">
            <span class="company">Porter Group</span>
            <span class="role">Software Engineer</span>
            <span class="period">Nov 2020 – Jun 2022 · Florianópolis, Brazil</span>
          </div>
          <p class="timeline-desc">Maintained real-time WebSocket systems for a monitoring platform and built a UI component library to standardize code across applications.</p>
        </div>
      </div>

      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-body">
          <div class="timeline-header">
            <span class="company">Sanar</span>
            <span class="role">Software Engineer</span>
            <span class="period">Apr 2020 – Aug 2020 · Remote</span>
          </div>
          <p class="timeline-desc">Set up the initial tech stack and developed CRUD features integrated with GraphQL APIs, including media upload handling.</p>
        </div>
      </div>

      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-body">
          <div class="timeline-header">
            <span class="company">Sponte</span>
            <span class="role">Software Engineer</span>
            <span class="period">Feb 2019 – Apr 2020 · Dois Vizinhos, Brazil</span>
          </div>
          <p class="timeline-desc">Contributed to a UI component library and integrated backend APIs, with a focus on code quality through integration testing.</p>
        </div>
      </div>

      <div class="timeline-item last">
        <div class="timeline-dot"></div>
        <div class="timeline-body">
          <div class="timeline-header">
            <span class="company">Codengage</span>
            <span class="role">Intern</span>
            <span class="period">Oct 2018 – Feb 2020 · Dois Vizinhos, Brazil</span>
          </div>
          <p class="timeline-desc">Helped build a PWA UI, added a GraphQL integration to an existing API, and wrote unit and integration tests.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Events & Talks -->
  <section class="section last-section">
    <h2 class="section-title">Events &amp; Talks</h2>

    <article class="event">
      <span class="event-tag">Conference</span>
      <div class="event-header">
        <h3 class="event-title">TDC Innovation — Florianópolis</h3>
        <p class="event-date">2025</p>
      </div>

      <p class="body-text">Attended TDC Innovation in Florianópolis, one of the largest developer conferences in Brazil.</p>

      <figure class="photo">
        <img src="{base}/TDC_2.JPG" alt="TDC Innovation — Premium badge" />
        <figcaption>Leonardo Nicolai  #THEDEVCONF</figcaption>
      </figure>
    </article>
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
.back-link:hover {
  color: var(--color-text);
  border-color: var(--color-border);
  background: var(--color-tag-bg);
}
.back-icon { width: 12px; height: 12px; fill: currentColor; flex-shrink: 0; }

.detail-title {
  font-family: "Montserrat", sans-serif;
  font-size: 2rem;
  font-weight: 700;
  margin: 0 0 2.5rem 0;
  color: var(--color-text);
}

/* Sections */
.section { margin-bottom: 3rem; }
.section.last-section { margin-bottom: 0; }
.section-title {
  font-family: "Montserrat", sans-serif;
  font-size: 1rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--color-text-muted);
  margin: 0 0 1.5rem 0;
  padding-bottom: 0.5rem;
  border-bottom: 1px solid var(--color-border);
}

/* Timeline */
.timeline { display: flex; flex-direction: column; }
.timeline-item {
  display: flex;
  gap: 1.25rem;
  position: relative;
  padding-bottom: 2rem;
}
.timeline-item:not(.last)::before {
  content: '';
  position: absolute;
  left: 6px;
  top: 14px;
  bottom: 0;
  width: 1px;
  background: var(--color-border);
}
.timeline-dot {
  width: 13px;
  height: 13px;
  border-radius: 50%;
  background: var(--color-ruby);
  flex-shrink: 0;
  margin-top: 4px;
  position: relative;
  z-index: 1;
  box-shadow: 0 0 0 3px var(--color-bg);
}
.timeline-body { flex: 1; }
.timeline-header {
  display: flex;
  flex-wrap: wrap;
  align-items: baseline;
  gap: 0.5rem;
  margin-bottom: 0.6rem;
}
.company {
  font-family: "Montserrat", sans-serif;
  font-size: 1rem;
  font-weight: 700;
  color: var(--color-text-secondary);
}
.role {
  font-family: "Montserrat", sans-serif;
  font-size: 0.9rem;
  color: var(--color-text-muted);
  font-style: italic;
}
.period {
  font-family: "Montserrat", sans-serif;
  font-size: 0.78rem;
  color: var(--color-text-muted);
  margin-left: auto;
}
.timeline-desc {
  font-family: "Montserrat", sans-serif;
  font-size: 0.9rem;
  color: var(--color-text-secondary);
  line-height: 1.6;
  margin: 0;
}

/* Events */
.event {
  display: flex;
  flex-direction: column;
  gap: 0.6rem;
}

.event-tag {
  font-family: "Montserrat", sans-serif;
  font-size: 0.72rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--color-ruby);
}

.event-header {
  display: flex;
  flex-wrap: wrap;
  align-items: baseline;
  gap: 0.5rem;
}

.event-title {
  font-family: "Montserrat", sans-serif;
  font-size: 1rem;
  font-weight: 700;
  color: var(--color-text-secondary);
  margin: 0;
}

.event-date {
  font-family: "Montserrat", sans-serif;
  font-size: 0.78rem;
  color: var(--color-text-muted);
  margin: 0 0 0 auto;
}

.body-text {
  font-family: "Montserrat", sans-serif;
  font-size: 0.9rem;
  color: var(--color-text-secondary);
  line-height: 1.6;
  margin: 0;
}

/* Medium-style photo */
.photo {
  margin: 0.75rem 0 0 0;
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
