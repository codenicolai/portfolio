<script>
import { base } from "$app/paths";
import { skillIcons } from "$lib/skillIcons.js";

const skillGroups = [
	{
		label: "Main Stack",
		skills: [
			{ name: "React", icon: "react", flag: null },
			{ name: "Next.js", icon: "nextjs", flag: null },
			{ name: "TypeScript", icon: "typescript", flag: null },
			{ name: "Node.js", icon: "nodejs", flag: null },
		],
	},
	{
		label: "Other Frameworks",
		skills: [
			{ name: "React Native", icon: "reactnative", flag: null },
			{ name: "Nest.js", icon: "nestjs", flag: null },
			{ name: "Svelte", icon: "svelte", flag: null },
			{ name: "Electron", icon: "electron", flag: null },
		],
	},
	{
		label: "Libraries",
		skills: [
			{ name: "Zustand", icon: "zustand", flag: null },
			{ name: "Apollo GraphQL", icon: "apollographql", flag: null },
			{ name: "Styled Components", icon: "styledcomponents", flag: null },
			{ name: "Tailwind CSS", icon: "tailwind", flag: null },
			{ name: "TanStack Query", icon: "tanstack", flag: null },
			{ name: "React Testing Library", icon: "testinglibrary", flag: null },
			{ name: "Cypress", icon: "cypress", flag: null },
		],
	},
	{
		label: "APIs & Protocols",
		skills: [
			{ name: "GraphQL", icon: "graphql", flag: null },
			{ name: "REST APIs", icon: "restapis", flag: null },
			{ name: "WebSockets", icon: "websockets", flag: null },
			{ name: "OpenAI API", icon: "openai", flag: null },
		],
	},
	{
		label: "Infrastructure & Systems",
		skills: [
			{ name: "Docker", icon: "docker", flag: null },
			{ name: "Kubernetes", icon: "kubernetes", flag: null },
			{ name: "Kafka", icon: "kafka", flag: null },
			{ name: "Redis", icon: "redis", flag: null },
			{ name: "System Design", icon: "systemdesign", flag: null },
		],
	},
	{
		label: "Tools & Practices",
		skills: [
			{ name: "Git / GitHub", icon: "github", flag: null },
			{ name: "Vite", icon: "vite", flag: null },
			{ name: "Cucumber", icon: "cucumber", flag: null },
			{ name: "Storybook", icon: "storybook", flag: null },
			{ name: "Linux", icon: "linux", flag: null },
			{ name: "Scrum / Agile", icon: "agile", flag: null },
			{ name: "AI Agents", icon: "aiagents", flag: null },
			{ name: "LLM's", icon: "llms", flag: null },
		],
	},
	{
		label: "Languages",
		skills: [
			{ name: "Portuguese — Native", icon: null, flag: "🇧🇷" },
			{ name: "English — Fluent", icon: null, flag: "🇺🇸" },
		],
	},
];

// Shuffle each badge's entrance delay so they don't rise in left-to-right order.
const allSkills = skillGroups.flatMap((g) => g.skills);
const shuffledRanks = allSkills.map((_, i) => i);
for (let i = shuffledRanks.length - 1; i > 0; i--) {
	const j = Math.floor(Math.random() * (i + 1));
	[shuffledRanks[i], shuffledRanks[j]] = [shuffledRanks[j], shuffledRanks[i]];
}
const DELAY_STEP_MS = 22;
allSkills.forEach((skill, i) => {
	skill.delay = shuffledRanks[i] * DELAY_STEP_MS;
});
</script>

<main class="detail-container">
  <a href="{base}/" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>

  <h1 class="detail-title">Skills</h1>

  <div class="detail-content">
    <p class="intro">I'm a software engineer with 7+ years of experience building and leading scalable, AI-integrated products. From React/React Native frontends to Node.js/Express APIs and some SQL too. I'm experienced working on the design side too, which I really like.</p>


    {#each skillGroups as group}
      <div class="skills-group">
        <h3 class="group-label">{group.label}</h3>
        <div class="tags">
          {#each group.skills as skill}
            <span class="tag" style="animation-delay: {skill.delay}ms">
              {#if skill.flag}
                <span class="tag-icon tag-flag">{skill.flag}</span>
              {:else if skill.icon}
                <span class="tag-icon" class:tag-icon-colorful={group.label === 'Main Stack'} data-icon={skill.icon}>{@html skillIcons[skill.icon]}</span>
              {/if}
              {skill.name}
            </span>
          {/each}
        </div>
      </div>
    {/each}
  </div>

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
        </div>
      </div>
    </div>
  </section>
</main>

<style>
.detail-container {
  width: 40vw;
  margin: 2rem auto 4rem auto;
  display: flex;
  flex-direction: column;
}
@media (max-width: 768px) {
  .detail-container { width: 88vw; }
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
  color: var(--color-text);
  border-color: var(--color-border);
  background: var(--color-tag-bg);
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
  margin: 0 0 2rem 0;
  color: var(--color-text);
}

@keyframes rise-in {
  from {
    opacity: 0;
    transform: translateY(58px) scale(0.94);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

@media (prefers-reduced-motion: reduce) {
  .detail-title,
  .tag {
    animation: none;
  }
}

.detail-content {
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
  margin-bottom: 3rem;
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
.tags { display: flex; flex-wrap: wrap; gap: 0.4rem; overflow: hidden; padding-bottom: 2px; }
.tag {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  font-family: "Montserrat", sans-serif;
  font-size: 0.78rem;
  font-weight: 600;
  background: var(--color-tag-bg);
  color: var(--color-tag-text);
  border-radius: 999px;
  padding: 0.3rem 0.8rem 0.3rem 0.6rem;
  animation: rise-in 0.54s cubic-bezier(0.33, 1, 0.68, 1) both;
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
.tag-icon-colorful[data-icon="react"] { color: #61dafb; }
.tag-icon-colorful[data-icon="nextjs"] { color: var(--color-text); }
.tag-icon-colorful[data-icon="typescript"] { color: #3178c6; }
.tag-icon-colorful[data-icon="nodejs"] { color: #539e43; }
.tag-icon-colorful[data-icon="python"] { color: #ffd43b; }
.tag-flag {
  font-size: 0.85rem;
  line-height: 1;
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
  background: var(--color-sapphire);
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
</style>
