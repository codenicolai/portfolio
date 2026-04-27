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

  <h1 class="detail-title">Projects</h1>
  <p class="detail-date">February, 2026</p>

  <!-- 1 -->
  <article class="project">
    <div class="project-top">
      <div>
        <span class="project-tag">UI · Design System</span>
        <h2 class="project-name">Sponte — Design System & Component Library</h2>
        <p class="project-desc">Scalable component library to standardize UI development and accelerate delivery across applications.</p>
      </div>
    </div>
    <div class="tags">
      <span class="tag">React</span>
      <span class="tag">TypeScript</span>
      <span class="tag">Storybook</span>
      <span class="tag">Styled Components</span>
    </div>
    <ul class="contributions">
      <li>Reusable UI components — lists, loaders, skeletons, feedback states</li>
      <li>Standardized visual and interaction patterns with accessibility in mind</li>
      <li>Scalable structure handling all UI states: loading, empty, error, success</li>
    </ul>
    <p class="highlight">Strong focus on UX states and component scalability — thinking beyond visuals.</p>
  </article>

  <div class="divider"></div>

  <!-- 2 -->
  <article class="project">
    <div class="project-top">
      <div>
        <span class="project-tag">Real-Time · Infrastructure</span>
        <h2 class="project-name">Real-Time Monitoring Platform</h2>
        <p class="project-desc">Monitoring system for buildings and commercial spaces with live data streams and remote control of doors, gates, and security systems.</p>
      </div>
    </div>
    <div class="tags">
      <span class="tag">React</span>
      <span class="tag">WebSockets</span>
      <span class="tag">Node.js</span>
    </div>
    <ul class="contributions">
      <li>Real-time UI powered by WebSockets with live status for multiple devices</li>
      <li>Responsive dashboards designed for continuous monitoring</li>
      <li>Managed connection stability and high-frequency update performance</li>
    </ul>
    <p class="highlight">Heavy use of WebSockets and real-time architecture patterns.</p>
  </article>

  <div class="divider"></div>

  <!-- 3 -->
  <article class="project">
    <div class="project-top">
      <div>
        <span class="project-tag">AI · Governance</span>
        <h2 class="project-name">Atlas Governance — AI-Powered Meeting Platform</h2>
        <p class="project-desc">Corporate governance platform for managing assemblies, discussions, and voting — enhanced with AI for communication and decision-making.</p>
      </div>
    </div>
    <div class="tags">
      <span class="tag">React</span>
      <span class="tag">WebSockets</span>
      <span class="tag">OpenAI API</span>
      <span class="tag">Zoom SDK</span>
    </div>
    <ul class="contributions">
      <li>AI integration for real-time transcription, summarization, and translation</li>
      <li>Meeting assistant with AI listening and live chat interaction</li>
      <li>Full video call system integration alongside AI and chat layers</li>
    </ul>
    <p class="highlight">End-to-end integration of AI into real-time collaborative environments.</p>
  </article>

  <div class="divider"></div>

  <!-- 4 -->
  <article class="project">
    <div class="project-top">
      <div>
        <span class="project-tag">AI · Veterinary · Desktop</span>
        <h2 class="project-name">Ultrasound Report Reader</h2>
        <p class="project-desc">Desktop app that reads veterinary ultrasound images and extracts structured metrics — measurements, tissue observations, diagnostic notes — then exports a clean report.</p>
      </div>
    </div>
    <div class="tags">
      <span class="tag">Electron</span>
      <span class="tag">JavaScript</span>
      <span class="tag">OpenAI API</span>
    </div>
    <ul class="contributions">
      <li>OpenAI Vision API integration with structured prompt engineering</li>
      <li>Desktop interface built with Electron for local file processing</li>
      <li>Automated extraction and exportable structured report output</li>
    </ul>
    <p class="highlight">Combination of desktop development and document intelligence for veterinary use.</p>
  </article>

  <div class="divider"></div>

  <!-- 5 -->
  <article class="project">
    <div class="project-top">
      <div>
        <span class="project-tag">Performance · Data</span>
        <h2 class="project-name">Atlas Governance — Large-Scale CSV Handling</h2>
        <p class="project-desc">Feature built to handle and render datasets exceeding 500k rows, directly in the browser without crashing or degrading the user experience.</p>
      </div>
    </div>
    <div class="tags">
      <span class="tag">React</span>
      <span class="tag">Virtualization</span>
      <span class="tag">CSV parsing</span>
    </div>
    <ul class="contributions">
      <li>Implemented virtual rendering to handle 500k+ row datasets</li>
      <li>Optimized parsing and state management to avoid UI blocking</li>
      <li>Maintained smooth interaction under continuous data load</li>
    </ul>
    <p class="highlight">Pushing the browser's limits with large data — performance as a feature.</p>
  </article>
</main>

<style>
.detail-container {
  width: 60vw;
  margin: 2rem auto 4rem auto;
  display: flex;
  flex-direction: column;
  gap: 0;
}
@media (max-width: 768px) { .detail-container { width: 88vw; } }

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
  margin: 0 0 2.5rem 0;
}

/* Project */
.project {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 0.25rem 0 2rem 0;
}

.project-tag {
  font-family: "Montserrat", sans-serif;
  font-size: 0.7rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--color-accent);
  display: block;
  margin-bottom: 0.35rem;
}

.project-name {
  font-family: "Montserrat", sans-serif;
  font-size: 1.15rem;
  font-weight: 700;
  color: var(--color-text-secondary);
  margin: 0 0 0.5rem 0;
}

.project-desc {
  font-family: "Montserrat", sans-serif;
  font-size: 0.95rem;
  color: var(--color-text-muted);
  line-height: 1.65;
  margin: 0;
}

/* Stack tags */
.tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }
.tag {
  font-family: "Montserrat", sans-serif;
  font-size: 0.75rem;
  font-weight: 600;
  background: var(--color-tag-bg);
  color: var(--color-tag-text);
  border-radius: 999px;
  padding: 0.22rem 0.7rem;
}

/* Contributions */
.contributions {
  margin: 0;
  padding-left: 1.1rem;
  display: flex;
  flex-direction: column;
  gap: 0.3rem;
}
.contributions li {
  font-family: "Montserrat", sans-serif;
  font-size: 0.88rem;
  color: var(--color-text-secondary);
  line-height: 1.6;
}

/* Highlight */
.highlight {
  font-family: "Montserrat", sans-serif;
  font-size: 0.82rem;
  color: var(--color-text-muted);
  font-style: italic;
  border-left: 2px solid var(--color-accent);
  padding-left: 0.75rem;
  margin: 0;
}

/* Screenshot */
.project-screenshot img {
  width: 100%;
  border-radius: 10px;
  display: block;
  box-shadow: 0 4px 20px var(--color-img-shadow);
  object-fit: cover;
}

/* Divider */
.divider {
  width: 100%;
  height: 1px;
  background: var(--color-border);
  margin: 0.5rem 0 1.75rem 0;
}
</style>
