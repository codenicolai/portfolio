<script>
import { base } from "$app/paths";
import { skillIcons } from "$lib/skillIcons.js";
import Seo from "$lib/components/Seo.svelte";
import grana1 from "$lib/assets/grana1.png";
import grana2 from "$lib/assets/grana2.png";
import agm1 from "$lib/assets/agm1.png";
import agm2 from "$lib/assets/agm2.png";
import agm3 from "$lib/assets/agm3.png";
import agm4 from "$lib/assets/agm4.png";
import agm5 from "$lib/assets/agm5.png";
import agm6 from "$lib/assets/agm6.png";
import agm7 from "$lib/assets/agm7.png";
import agm8 from "$lib/assets/agm8.png";
import agm9 from "$lib/assets/agm9.png";
import agm10 from "$lib/assets/agm10.png";
import csv1 from "$lib/assets/csv1.png";
import csv2 from "$lib/assets/csv2.png";
import csv3 from "$lib/assets/csv3.png";

const categories = ["All", "AI", "Frontend", "Websockets", "UX/UI"];

const projects = [
	{
		tag: "Performance · Data",
		name: "Large-Scale CSV Handling",
		desc: "Frontend that makes datasets exceeding 500k rows viewable in real time, directly in the browser, without crashing or degrading the user experience. Built infinite scroll and dynamic loading to render the dataset, optimized parsing and state management to avoid UI blocking, and maintained smooth interaction under continuous data load.",
		techs: [
			{ icon: "react", label: "React" },
			{ icon: "infinitescroll", label: "Infinite Scroll" },
			{ icon: "csvparsing", label: "CSV parsing" },
		],
		highlight:
			"500K-row dataset made browsable through infinite scroll and dynamic loading.",
		categories: ["Frontend"],
		screenshots: [csv1, csv2, csv3],
	},
	{
		tag: "UI · Design System",
		name: "Brand new Design System & Component Library",
		desc: "Scalable component library to standardize UI development and accelerate delivery across applications, with reusable components (lists, loaders, skeletons, feedback states) built on standardized visual and interaction patterns with accessibility in mind, and a structure that handles every UI state: loading, empty, error, and success.",
		techs: [
			{ icon: "react", label: "React" },
			{ icon: "typescript", label: "TypeScript" },
			{ icon: "storybook", label: "Storybook" },
			{ icon: "styledcomponents", label: "Styled Components" },
		],
		highlight:
			"Strong focus on UX states and component scalability, thinking beyond visuals.",
		categories: ["Frontend"],
	},
	{
		tag: "Real-Time · Infrastructure",
		name: "Real-Time Monitoring Platform",
		desc: "Home security platform with live WebSocket updates, used by 100+ concurrent call-center agents monitoring doors, gates, and alarm status in real time. Built a real-time UI with live status for multiple devices, responsive dashboards for continuous monitoring, and stable connections under high-frequency updates.",
		techs: [
			{ icon: "react", label: "React" },
			{ icon: "nextjs", label: "Next.js" },
			{ icon: "websockets", label: "WebSockets" },
			{ icon: "nodejs", label: "Node.js" },
			{ icon: "redis", label: "Redis" },
		],
		highlight:
			"Used by 100+ concurrent call-center agents handling high-frequency updates per minute.",
		categories: ["Websockets", "Frontend"],
	},
	{
		tag: "AI · Governance",
		name: "AI-Powered Meeting Platform",
		desc: "Corporate governance platform for managing assemblies, discussions, and voting, enhanced with AI for real-time transcription, summarization, and translation. Includes a meeting assistant with AI listening and live chat, a full video call system integrated alongside the AI and chat layers, and a PDF-to-assembly generation feature that auto-extracts shareholder meeting data.",
		techs: [
			{ icon: "react", label: "React" },
			{ icon: "reactnative", label: "React Native" },
			{ icon: "websockets", label: "WebSockets" },
			{ icon: "openai", label: "OpenAI API" },
			{ icon: "zoomsdk", label: "Zoom SDK" },
		],
		highlight:
			"70% faster registration for complex assemblies, by automating assembly creation from PDF documents.",
		categories: ["AI", "Websockets"],
		screenshots: [agm1, agm2, agm3, agm4, agm5, agm6, agm7, agm8, agm9, agm10],
	},
	{
		tag: "Performance · Frontend",
		name: "Frontend Performance",
		desc: "Bundle size audit and cleanup for the platform's core Vite application, targeting load performance. Audited and removed barrel-file re-exports across the codebase, re-structured module imports to enable proper tree-shaking, and validated the gains with bundle analysis before and after the change.",
		techs: [
			{ icon: "react", label: "React" },
			{ icon: "vite", label: "Vite" },
			{ icon: "performance", label: "Performance" },
		],
		highlight: "50% smaller production bundle after removing barrel files.",
		categories: ["Frontend"],
	},
	{
		tag: "AI · Veterinary · Desktop",
		name: "Ultrasound Report Reader",
		desc: "Desktop app that reads veterinary ultrasound images and extracts structured metrics (measurements, tissue observations, diagnostic notes), then exports a clean report. Built with Electron for local file processing and OpenAI Vision API integration with structured prompt engineering, automating extraction into an exportable report.",
		techs: [
			{ icon: "electron", label: "Electron" },
			{ icon: "javascript", label: "JavaScript" },
			{ icon: "openai", label: "OpenAI API" },
		],
		highlight:
			"Combination of desktop development and document intelligence for veterinary use.",
		categories: ["AI", "Frontend"],
	},
	{
		tag: "Personal · Mobile",
		name: "Finance App",
		desc: "Personal project for tracking income, expenses, and budgets in a single mobile app, built end-to-end from design to release.",
		techs: [
			{ icon: "flutter", label: "Flutter" },
			{ icon: "dart", label: "Dart" },
			{ icon: "uidesign", label: "UI/UX Design" },
		],
		highlight:
			"First personal project built with Flutter, outside of the usual JS/TS stack.",
		categories: ["Frontend", "UX/UI"],
		screenshots: [grana1, grana2],
	},
	{
		tag: "Desktop · Cross-Platform",
		name: "Windows game port to macOS",
		desc: "Ported the Windows-only game to run natively on macOS, without relying on Windows emulation. Diagnosed a Java environment check that only validated Windows-style paths, then built a cross-platform runtime handler that checks macOS install locations and PATH before falling back to the original Windows logic, adapting launch and file-handling so the game runs natively.",
		techs: [
			{ icon: "java", label: "Java" },
			{ icon: "macos", label: "macOS" },
		],
		highlight:
			"Unblocked a Windows-only desktop game to run natively on macOS by replacing a hardcoded Windows-path check with a portable Java runtime handler.",
		categories: ["AI"],
	},
];

let selected = $state("All");
const filteredProjects = $derived(
	(selected === "All"
		? projects
		: projects.filter((p) => p.categories.includes(selected))
	)
		.slice()
		.sort((a, b) => (b.screenshots ? 1 : 0) - (a.screenshots ? 1 : 0)),
);

/** @type {string[] | null} */
let activeGallery = $state(null);
let activeIndex = $state(0);

/** @param {{ screenshots?: string[] }} project */
function openGallery(project) {
	activeGallery = project.screenshots ?? null;
	activeIndex = 0;
}

function closeGallery() {
	activeGallery = null;
}

function nextImage() {
	if (!activeGallery) return;
	activeIndex = (activeIndex + 1) % activeGallery.length;
}

function prevImage() {
	if (!activeGallery) return;
	activeIndex = (activeIndex - 1 + activeGallery.length) % activeGallery.length;
}

/** @param {KeyboardEvent} e */
function handleKeydown(e) {
	if (!activeGallery) return;
	if (e.key === "Escape") closeGallery();
	else if (e.key === "ArrowRight") nextImage();
	else if (e.key === "ArrowLeft") prevImage();
}
</script>

<svelte:window onkeydown={handleKeydown} />

<Seo
  title="Projects"
  description="AI-powered platforms, design systems, real-time monitoring, and performance work by Leonardo Nicolai."
  path="/projects"
/>

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
      {#if project.screenshots}
        <button
          type="button"
          class="card-overlay-link"
          tabindex="-1"
          aria-hidden="true"
          onclick={() => openGallery(project)}
        ></button>
      {/if}
      <div class="project-top">
        <div>
          <span class="project-tag">{project.tag}</span>
          <div class="project-name-row">
            <h2 class="project-name">{project.name}</h2>
            {#if project.screenshots}
              <button
                type="button"
                class="gallery-btn"
                aria-label="View screenshots for {project.name}"
                onclick={() => openGallery(project)}
              >
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
                  <rect x="3" y="3" width="18" height="18" rx="2" />
                  <circle cx="9" cy="9" r="2" />
                  <path d="m21 15-3.086-3.086a2 2 0 0 0-2.828 0L6 21" />
                </svg>
              </button>
            {/if}
          </div>
          <p class="project-desc">{project.desc}</p>
        </div>
      </div>
      <div class="tags">
        {#each project.techs as tech}
          <span class="tag"><span class="tag-icon">{@html skillIcons[tech.icon]}</span>{tech.label}</span>
        {/each}
      </div>
    </article>
    {#if i < filteredProjects.length - 1}
      <div class="divider"></div>
    {/if}
  {/each}
</main>

{#if activeGallery}
  <div class="modal-overlay" onclick={closeGallery} role="presentation">
    <div class="modal-content" role="presentation" onclick={(e) => e.stopPropagation()}>
      <button type="button" class="modal-close" aria-label="Close" onclick={closeGallery}>
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
          <line x1="18" y1="6" x2="6" y2="18" />
          <line x1="6" y1="6" x2="18" y2="18" />
        </svg>
      </button>

      {#if activeGallery.length > 1}
        <button type="button" class="modal-nav modal-nav-prev" aria-label="Previous image" onclick={prevImage}>
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
            <polyline points="15 18 9 12 15 6" />
          </svg>
        </button>
      {/if}

      <img class="modal-image" src={activeGallery[activeIndex]} alt="Screenshot {activeIndex + 1}" />

      {#if activeGallery.length > 1}
        <button type="button" class="modal-nav modal-nav-next" aria-label="Next image" onclick={nextImage}>
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
            <polyline points="9 18 15 12 9 6" />
          </svg>
        </button>
        <div class="modal-counter">{activeIndex + 1} / {activeGallery.length}</div>
      {/if}
    </div>
  </div>
{/if}

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
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 0.65rem;
  padding: 0.25rem 0 1.1rem 0;
  margin-bottom: 20px;
}

.card-overlay-link {
  position: absolute;
  inset: 0;
  z-index: 1;
  width: 100%;
  height: 100%;
  padding: 0;
  margin: 0;
  border: none;
  background: transparent;
  cursor: pointer;
}
.card-overlay-link:focus-visible {
  outline: 2px solid var(--color-sapphire);
  outline-offset: 4px;
  border-radius: 10px;
}

.project-tag {
  font-family: "Montserrat", sans-serif;
  font-size: 0.7rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--color-sapphire);
  display: block;
  margin-bottom: 0.3rem;
}

.project-name-row {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin: 0 0 0.35rem 0;
}

.project-name {
  font-family: "Montserrat", sans-serif;
  font-size: 1.15rem;
  font-weight: 700;
  color: var(--color-text-secondary);
  margin: 0;
}

.gallery-btn {
  position: relative;
  z-index: 2;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 24px;
  height: 24px;
  padding: 0;
  border: none;
  background: transparent;
  color: var(--color-text-muted);
  cursor: pointer;
  flex-shrink: 0;
  transition: color 0.2s;
}
.gallery-btn:hover {
  color: var(--color-sapphire);
}
.gallery-btn svg {
  width: 16px;
  height: 16px;
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

/* Divider */
.divider {
  width: 100%;
  height: 1px;
  background: var(--color-border);
  margin: 0.4rem 0 1rem 0;
}

/* Gallery modal */
.modal-overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.75);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 100;
  padding: 3rem 2rem;
  box-sizing: border-box;
}

.modal-content {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  max-width: min(90vw, 560px);
  max-height: 100%;
}

.modal-image {
  max-width: 100%;
  max-height: 80vh;
  border-radius: 10px;
  display: block;
  box-shadow: 0 8px 40px rgba(0, 0, 0, 0.5);
}

.modal-close {
  position: absolute;
  top: -2.5rem;
  right: 0;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  padding: 0;
  border: none;
  background: transparent;
  color: #fff;
  cursor: pointer;
}
.modal-close svg { width: 20px; height: 20px; }

.modal-nav {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 999px;
  border: none;
  background: rgba(0, 0, 0, 0.5);
  color: #fff;
  cursor: pointer;
  transition: background 0.2s;
}
.modal-nav:hover { background: rgba(0, 0, 0, 0.7); }
.modal-nav svg { width: 20px; height: 20px; }
.modal-nav-prev { left: -1.25rem; }
.modal-nav-next { right: -1.25rem; }

.modal-counter {
  position: absolute;
  bottom: -2.25rem;
  left: 50%;
  transform: translateX(-50%);
  font-family: "Montserrat", sans-serif;
  font-size: 0.82rem;
  color: #fff;
}
</style>
