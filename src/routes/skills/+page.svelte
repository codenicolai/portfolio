<main class="detail-container">
  <a href="/" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>

  <h1 class="detail-title">Skills</h1>
  <p class="detail-date">January 18, 2026</p>

  <div class="detail-layout">
    <div class="detail-image">
      <img src="https://images.unsplash.com/photo-1516116216624-53e697fedbea?w=700&q=80" alt="Skills" />
    </div>
    <div class="detail-content">
      <p class="intro">Software engineer with 8+ years of experience building scalable products, leading teams, and shipping quality front-end and full-stack applications.</p>

      <div class="skills-group">
        <h3 class="group-label">Frontend</h3>
        <div class="tags">
          <span class="tag">React.js</span>
          <span class="tag">React Native</span>
          <span class="tag">Electron</span>
          <span class="tag">TypeScript</span>
          <span class="tag">JavaScript</span>
          <span class="tag">Svelte</span>
          <span class="tag">CSS / SASS</span>
          <span class="tag">HTML5</span>
          <span class="tag">Bootstrap</span>
           <span class="tag">Zustand</span>
          <span class="tag">Responsive Design</span>
        </div>
      </div>

      <div class="skills-group">
        <h3 class="group-label">Backend & APIs</h3>
        <div class="tags">
          <span class="tag">Node.js</span>
          <span class="tag">GraphQL</span>
          <span class="tag">Apollo GraphQL</span>
          <span class="tag">REST APIs</span>
          <span class="tag">Flask</span>
         
        </div>
      </div>

      <div class="skills-group">
        <h3 class="group-label">Tools & Practices</h3>
        <div class="tags">
          <span class="tag">Git / GitHub</span>
          <span class="tag">Vite</span>
          <span class="tag">Cypress</span>
          <span class="tag">Cucumber</span>
          <span class="tag">Linux</span>
          <span class="tag">Scrum / Agile</span>
          <span class="tag">AI Agents</span>
          <span class="tag">LLM's</span>
         
        </div>
      </div>

      <div class="skills-group">
        <h3 class="group-label">Languages</h3>
        <div class="tags">
          <span class="tag">Portuguese — Native</span>
          <span class="tag">English — Fluent</span>
        </div>
      </div>
    </div>
  </div>

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
          <p class="timeline-desc">Led frontend architecture and team delivery. Built AI integrations for translation, transcription, and summarization, and designed features handling large-scale datasets.</p>
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

      <div class="timeline-item">
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

  <!-- Education -->
  <section class="section">
    <h2 class="section-title">Education</h2>
    <div class="timeline">
      <div class="timeline-item last">
        <div class="timeline-dot"></div>
        <div class="timeline-body">
          <div class="timeline-header">
            <span class="company">UTFPR</span>
            <span class="role">Bachelor's Degree in Computer Science</span>
            <span class="period">Jan 2015 – Dec 2020 · Dois Vizinhos, Brazil</span>
          </div>
          <p class="timeline-desc">Involved in a Junior Company Project as part of the curriculum, contributing to real-world software development, project management, and team collaboration.</p>
        </div>
      </div>
    </div>
  </section>
</main>

<style>
.detail-container {
  width: 60vw;
  margin: 2rem auto 4rem auto;
  display: flex;
  flex-direction: column;
}
@media (max-width: 768px) {
  .detail-container { width: 88vw; }
  .detail-layout { flex-direction: column; }
  .detail-image img { width: 100%; height: 220px; }
}

/* Back button */
.back-link {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  font-family: "Montserrat", sans-serif;
  font-size: 0.82rem;
  font-weight: 600;
  color: var(--color-text-muted);
  text-decoration: none;
  padding: 0.38rem 0.85rem 0.38rem 0.6rem;
  border-radius: 999px;
  border: 1px solid var(--color-border);
  background: transparent;
  transition: color 0.2s, border-color 0.2s, background 0.2s;
  margin-bottom: 1.5rem;
  align-self: flex-start;
}
.back-link:hover {
  color: var(--color-accent);
  border-color: var(--color-accent);
  background: var(--color-accent-subtle);
}
.back-icon {
  width: 12px;
  height: 12px;
  fill: currentColor;
  flex-shrink: 0;
}

/* Title */
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
  margin: 0 0 2rem 0;
}

/* Two-column layout */
.detail-layout {
  display: flex;
  gap: 2.5rem;
  align-items: flex-start;
  margin-bottom: 3rem;
}
.detail-image { flex: 0 0 40%; }
.detail-image img {
  width: 100%;
  height: 320px;
  object-fit: cover;
  border-radius: 14px;
  display: block;
  box-shadow: 0 4px 24px var(--color-img-shadow);
}
.detail-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
}
.intro {
  font-family: "Montserrat", sans-serif;
  font-size: 0.95rem;
  color: var(--color-text-secondary);
  line-height: 1.75;
  margin: 0;
}

/* Skill groups */
.skills-group { display: flex; flex-direction: column; gap: 0.5rem; }
.group-label {
  font-family: "Montserrat", sans-serif;
  font-size: 0.72rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--color-text-muted);
  margin: 0;
}
.tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }
.tag {
  font-family: "Montserrat", sans-serif;
  font-size: 0.78rem;
  font-weight: 600;
  background: var(--color-tag-bg);
  color: var(--color-tag-text);
  border-radius: 999px;
  padding: 0.25rem 0.75rem;
}

/* Sections */
.section { margin-bottom: 3rem; }
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
  background: var(--color-accent);
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
.timeline-list {
  margin: 0;
  padding-left: 1.2rem;
  display: flex;
  flex-direction: column;
  gap: 0.3rem;
}
.timeline-list li {
  font-family: "Montserrat", sans-serif;
  font-size: 0.9rem;
  color: var(--color-text-secondary);
  line-height: 1.6;
}
.timeline-desc {
  font-family: "Montserrat", sans-serif;
  font-size: 0.9rem;
  color: var(--color-text-secondary);
  line-height: 1.6;
  margin: 0;
}
</style>
