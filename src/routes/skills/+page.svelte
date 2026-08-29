<script>
import { base } from "$app/paths";
import { skillIcons } from "$lib/skillIcons.js";
import Seo from "$lib/components/Seo.svelte";

const certifications = [
	{
		name: "Claude Certified",
		issuer: "Anthropic",
		description:
			"Certified on building and integrating with Claude, Anthropic's AI models.",
		logo: "anthropic.svg",
		url: "https://academy.claude.com/verify/84ba4a0b1492a85d3033c71e86aaf478",
	},
	{
		name: "English C1 Advanced",
		issuer: "EF SET",
		description:
			"C1 (Advanced) English proficiency, certified by the EF SET English Certificate.",
		logo: "efset.svg",
		url: "https://cert.efset.org/pt/4w9K8g",
	},
	{
		name: "Gestão eficaz de projetos e equipes",
		issuer: "Santander Open Academy",
		description:
			"Project and team management course by Santander Open Academy.",
		logo: "santander.png",
		url: null,
	},
];

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
			{ name: "Portuguese (Native)", icon: null, flag: "🇧🇷" },
			{ name: "English (C1)", icon: null, flag: "🇺🇸" },
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

<Seo
  title="Skills"
  description="React, React Native, TypeScript, Node.js, and the tools Leonardo Nicolai uses to build AI-integrated products."
  path="/skills"
/>

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

  <!-- Certifications -->
  <section class="section">
    <h2 class="section-title">Certifications</h2>
    <div class="cert-list">
      {#each certifications as cert}
        <svelte:element this={cert.url ? "a" : "div"} class="cert-row" href={cert.url} target={cert.url ? "_blank" : undefined} rel={cert.url ? "noopener noreferrer" : undefined}>
          <span class="cert-logo">
            <img src="{base}/logos/{cert.logo}" alt="{cert.issuer} logo" />
          </span>
          <span class="cert-info">
            <span class="cert-header">
              <span class="cert-name">{cert.name}</span>
              <span class="cert-issuer">{cert.issuer}</span>
            </span>
            <span class="cert-description">{cert.description}</span>
          </span>
        </svelte:element>
      {/each}
    </div>
  </section>

  <!-- Education -->
  <section class="section">
    <h2 class="section-title">Education</h2>
    <div class="timeline">
      <div class="timeline-item last">
        <a class="timeline-logo" href="https://www.utfpr.edu.br" target="_blank" rel="noopener noreferrer" aria-label="UTFPR website">
          <img src="{base}/logos/utfpr.svg" alt="UTFPR logo" />
        </a>
        <div class="timeline-body">
          <div class="timeline-header">
            <span class="company">UTFPR</span>
            <span class="role">Bachelor's Degree in Computer Science</span>
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

/* Certifications */
.cert-list {
  display: flex;
  flex-direction: column;
}
.cert-row {
  display: flex;
  align-items: center;
  gap: 0.85rem;
  padding: 0.9rem 0;
  text-decoration: none;
}
a.cert-row {
  cursor: pointer;
}
.cert-logo {
  width: 36px;
  height: 36px;
  border-radius: 9px;
  background: #ffffff;
  border: 1px solid var(--color-border);
  flex-shrink: 0;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 5px;
}
.cert-logo img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}
.cert-info {
  display: flex;
  flex-direction: column;
  gap: 0.2rem;
  min-width: 0;
}
.cert-header {
  display: flex;
  flex-wrap: wrap;
  align-items: baseline;
  gap: 0.4rem;
}
.cert-name {
  font-family: "Montserrat", sans-serif;
  font-size: 0.85rem;
  font-weight: 700;
  color: var(--color-text-secondary);
  line-height: 1.3;
}
.cert-issuer {
  font-family: "Montserrat", sans-serif;
  font-size: 0.75rem;
  color: var(--color-text-muted);
}
.cert-description {
  font-family: "Montserrat", sans-serif;
  font-size: 0.78rem;
  color: var(--color-text-muted);
  line-height: 1.4;
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
  left: 17px;
  top: 38px;
  bottom: 0;
  width: 1px;
  background: var(--color-border);
}
.timeline-logo {
  width: 36px;
  height: 36px;
  border-radius: 9px;
  background: #ffffff;
  border: 1px solid var(--color-border);
  flex-shrink: 0;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  z-index: 1;
  cursor: pointer;
  padding: 5px;
  transition: transform 0.2s;
}
.timeline-logo:hover {
  transform: scale(1.06);
}
.timeline-logo img {
  width: 100%;
  height: 100%;
  object-fit: contain;
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
