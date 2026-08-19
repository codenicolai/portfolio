<script>
  import { base } from '$app/paths';
  import { skillIcons } from '$lib/skillIcons.js';

  const categories = ['All', 'AI', 'Frontend', 'Websockets', 'Backend'];

  const projects = [
    {
      tag: 'UI · Design System',
      name: 'Sponte: Design System & Component Library',
      desc: 'Scalable component library to standardize UI development and accelerate delivery across applications.',
      techs: [
        { icon: 'react', label: 'React' },
        { icon: 'typescript', label: 'TypeScript' },
        { icon: 'storybook', label: 'Storybook' },
        { icon: 'styledcomponents', label: 'Styled Components' }
      ],
      contributions: [
        'Reusable UI components: lists, loaders, skeletons, feedback states',
        'Standardized visual and interaction patterns with accessibility in mind',
        'Scalable structure handling all UI states: loading, empty, error, success'
      ],
      highlight: 'Strong focus on UX states and component scalability, thinking beyond visuals.',
      categories: ['Frontend']
    },
    {
      tag: 'Real-Time · Infrastructure',
      name: 'Real-Time Monitoring Platform',
      desc: 'Home security platform with live WebSocket updates, used by 100+ concurrent call-center agents monitoring doors, gates, and alarm status in real time.',
      techs: [
        { icon: 'react', label: 'React' },
        { icon: 'nextjs', label: 'Next.js' },
        { icon: 'websockets', label: 'WebSockets' },
        { icon: 'nodejs', label: 'Node.js' },
        { icon: 'redis', label: 'Redis' }
      ],
      contributions: [
        'Real-time UI powered by WebSockets with live status for multiple devices',
        'Responsive dashboards designed for continuous monitoring',
        'Maintained connection stability under high-frequency updates per minute'
      ],
      highlight: 'Used by 100+ concurrent call-center agents handling high-frequency updates per minute.',
      categories: ['Websockets', 'Backend', 'Frontend']
    },
    {
      tag: 'AI · Governance',
      name: 'Atlas Governance: AI-Powered Meeting Platform',
      desc: 'Corporate governance platform for managing assemblies, discussions, and voting, enhanced with AI for communication and decision-making.',
      techs: [
        { icon: 'react', label: 'React' },
        { icon: 'websockets', label: 'WebSockets' },
        { icon: 'openai', label: 'OpenAI API' },
        { icon: 'zoomsdk', label: 'Zoom SDK' }
      ],
      contributions: [
        'AI integration for real-time transcription, summarization, and translation',
        'Meeting assistant with AI listening and live chat interaction',
        'Full video call system integration alongside AI and chat layers',
        'Built a PDF-to-assembly generation feature, auto-extracting shareholder meeting data'
      ],
      highlight: '70% faster registration for complex assemblies, by automating assembly creation from PDF documents.',
      categories: ['AI', 'Websockets', 'Backend']
    },
    {
      tag: 'Performance · Frontend',
      name: 'Atlas Governance: Frontend Performance',
      desc: "Bundle size audit and cleanup for the platform's core Vite application, targeting load performance.",
      techs: [
        { icon: 'react', label: 'React' },
        { icon: 'vite', label: 'Vite' },
        { icon: 'performance', label: 'Performance' }
      ],
      contributions: [
        'Audited and removed barrel-file re-exports across the codebase',
        'Re-structured module imports to enable proper tree-shaking',
        'Validated gains with bundle analysis before and after the change'
      ],
      highlight: '50% smaller production bundle after removing barrel files.',
      categories: ['Frontend']
    },
    {
      tag: 'AI · Veterinary · Desktop',
      name: 'Ultrasound Report Reader',
      desc: 'Desktop app that reads veterinary ultrasound images and extracts structured metrics (measurements, tissue observations, diagnostic notes), then exports a clean report.',
      techs: [
        { icon: 'electron', label: 'Electron' },
        { icon: 'javascript', label: 'JavaScript' },
        { icon: 'openai', label: 'OpenAI API' }
      ],
      contributions: [
        'OpenAI Vision API integration with structured prompt engineering',
        'Desktop interface built with Electron for local file processing',
        'Automated extraction and exportable structured report output'
      ],
      highlight: 'Combination of desktop development and document intelligence for veterinary use.',
      categories: ['AI', 'Frontend']
    },
    {
      tag: 'Performance · Data',
      name: 'Atlas Governance: Large-Scale CSV Handling',
      desc: 'Frontend that makes datasets exceeding 500k rows viewable in real time, directly in the browser, without crashing or degrading the user experience.',
      techs: [
        { icon: 'react', label: 'React' },
        { icon: 'infinitescroll', label: 'Infinite Scroll' },
        { icon: 'csvparsing', label: 'CSV parsing' }
      ],
      contributions: [
        'Built infinite scroll and dynamic loading to render 500k+ row datasets',
        'Optimized parsing and state management to avoid UI blocking',
        'Maintained smooth interaction under continuous data load'
      ],
      highlight: '500K-row dataset made browsable through infinite scroll and dynamic loading.',
      categories: ['Frontend']
    },
    {
      tag: 'Personal · Mobile',
      name: 'Personal Finance App',
      desc: 'Personal project for tracking personal income, expenses, and budgets.',
      techs: [
        { icon: 'flutter', label: 'Flutter' },
        { icon: 'dart', label: 'Dart' }
      ],
      contributions: [
        'Income, expense, and budget tracking in a single mobile app',
        'Built end-to-end as a personal project, from design to release'
      ],
      highlight: 'First personal project built with Flutter, outside of the usual JS/TS stack.',
      categories: ['Frontend']
    }
  ];

  let selected = $state('All');
  const filteredProjects = $derived(
    selected === 'All' ? projects : projects.filter((p) => p.categories.includes(selected))
  );
</script>

<main class="detail-container">
  <a href="{base}/" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>

  <h1 class="detail-title">Projects</h1>

  <div class="filters">
    {#each categories as cat}
      <button
        type="button"
        class="filter-btn"
        class:active={selected === cat}
        onclick={() => (selected = cat)}
      >
        {cat}
      </button>
    {/each}
  </div>

  {#each filteredProjects as project, i}
    <article class="project">
      <div class="project-top">
        <div>
          <span class="project-tag">{project.tag}</span>
          <h2 class="project-name">{project.name}</h2>
          <p class="project-desc">{project.desc}</p>
        </div>
      </div>
      <div class="tags">
        {#each project.techs as tech}
          <span class="tag"><span class="tag-icon">{@html skillIcons[tech.icon]}</span>{tech.label}</span>
        {/each}
      </div>
      <ul class="contributions">
        {#each project.contributions as line}
          <li>{line}</li>
        {/each}
      </ul>
      <p class="highlight">{project.highlight}</p>
    </article>
    {#if i < filteredProjects.length - 1}
      <div class="divider"></div>
    {/if}
  {/each}
</main>

<style>
.detail-container {
  width: 40vw;
  margin: 2rem auto 4rem auto;
  display: flex;
  flex-direction: column;
  gap: 0;
}
@media (max-width: 768px) { .detail-container { width: 88vw; } }

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
  margin: 0 0 1.25rem 0;
  color: var(--color-text);
}

/* Filters */
.filters {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1.75rem;
}
.filter-btn {
  font-family: "Montserrat", sans-serif;
  font-size: 0.78rem;
  font-weight: 600;
  color: var(--color-text-muted);
  background: transparent;
  border: 1px solid var(--color-border);
  border-radius: 999px;
  padding: 0.32rem 0.85rem;
  cursor: pointer;
  transition: color 0.2s, border-color 0.2s, background 0.2s;
}
.filter-btn:hover {
  color: var(--color-text);
  border-color: var(--color-text-muted);
}
.filter-btn.active {
  color: var(--color-bg);
  background: var(--color-text);
  border-color: var(--color-text);
}

/* Project */
.project {
  display: flex;
  flex-direction: column;
  gap: 0.65rem;
  padding: 0.25rem 0 1.1rem 0;
}

.project-tag {
  font-family: "Montserrat", sans-serif;
  font-size: 0.7rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--color-ruby);
  display: block;
  margin-bottom: 0.3rem;
}

.project-name {
  font-family: "Montserrat", sans-serif;
  font-size: 1.15rem;
  font-weight: 700;
  color: var(--color-text-secondary);
  margin: 0 0 0.35rem 0;
}

.project-desc {
  font-family: "Montserrat", sans-serif;
  font-size: 0.95rem;
  color: var(--color-text-muted);
  line-height: 1.5;
  margin: 0;
}

/* Stack tags */
.tags { display: flex; flex-wrap: wrap; gap: 0.5rem; }
.tag {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  font-family: "Montserrat", sans-serif;
  font-size: 0.75rem;
  font-weight: 600;
  background: var(--color-tag-bg);
  color: var(--color-tag-text);
  border-radius: 999px;
  padding: 0.32rem 0.8rem 0.32rem 0.6rem;
}
.tag-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 14px;
  height: 14px;
  flex-shrink: 0;
  color: var(--color-text-muted);
}
.tag-icon :global(svg) {
  width: 100%;
  height: 100%;
}

/* Contributions */
.contributions {
  margin: 0;
  padding-left: 1.1rem;
  display: flex;
  flex-direction: column;
  gap: 0.2rem;
}
.contributions li {
  font-family: "Montserrat", sans-serif;
  font-size: 0.88rem;
  color: var(--color-text-secondary);
  line-height: 1.45;
}

/* Highlight */
.highlight {
  font-family: "Montserrat", sans-serif;
  font-size: 0.82rem;
  color: var(--color-text-muted);
  font-style: italic;
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
  margin: 0.4rem 0 1rem 0;
}
</style>
