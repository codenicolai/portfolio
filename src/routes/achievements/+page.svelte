<script>
import { base } from "$app/paths";

const rawAchievements = [
	{
		stat: "50%",
		title: "Smaller Production Bundle",
		tag: "Performance · Frontend",
		desc: "Cut a Vite application's bundle size in half by auditing and removing barrel-file re-exports, improving load performance across the product.",
	},
	{
		stat: "70%",
		title: "Faster Complex Assembly Registration",
		tag: "AI · Product",
		desc: "Built an AI-powered feature that auto-generates shareholder assemblies from PDF documents, cutting registration time by up to 70% for complex assemblies.",
	},
	{
		stat: "3 yrs",
		title: "Leading a High-Performance Team",
		tag: "Leadership",
		desc: "Led a team of 6 developers and QAs for 3 years as Technical Lead, driving discovery, estimates, and delivery in a fast-paced, high-performance environment.",
	},
	{
		stat: "",
		title: "Dyte Sdk Migration to the Cloudflare Ecosystem",
		tag: "Infrastructure · Cross-Platform",
		desc: "Migrated the Dyte SDK to the Cloudflare ecosystem across both the React and React Native codebases, resolving cross-platform dependency chains, applying targeted patches, and adjusting CI/CD build configs to keep communication working on both platforms post-migration.",
	},
];

const achievements = rawAchievements.map((item) => {
	const match = item.stat.match(/^(\d+(?:\.\d+)?)(.*)$/);
	return {
		...item,
		statValue: match ? Number.parseFloat(match[1]) : 0,
		statSuffix: match ? match[2] : "",
	};
});

function countUp(node, { value, suffix, duration = 1800 }) {
	let started = false;

	function run() {
		let startTime = null;
		function step(ts) {
			if (startTime === null) startTime = ts;
			const progress = Math.min((ts - startTime) / duration, 1);
			const eased = 1 - (1 - progress) ** 5;
			const current = Math.round(value * eased);
			node.textContent = current + suffix;
			if (progress < 1) requestAnimationFrame(step);
		}
		requestAnimationFrame(step);
	}

	const observer = new IntersectionObserver(
		(entries) => {
			for (const entry of entries) {
				if (entry.isIntersecting && !started) {
					started = true;
					run();
					observer.disconnect();
				}
			}
		},
		{ threshold: 0.3 },
	);
	observer.observe(node);

	return {
		destroy() {
			observer.disconnect();
		},
	};
}
</script>

<main class="detail-container">
  <a href="{base}/" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>

  <h1 class="detail-title">Achievements</h1>

  {#each achievements as item, i}
    <article class="achievement">
      <span class="achievement-tag">{item.tag}</span>
      <div class="achievement-top">
        {#if item.stat}
          <span
            class="achievement-stat"
            use:countUp={{ value: item.statValue, suffix: item.statSuffix }}
          >0{item.statSuffix}</span>
        {/if}
        <h2 class="achievement-title">{item.title}</h2>
      </div>
      <p class="achievement-desc">{item.desc}</p>
    </article>
    {#if i < achievements.length - 1}
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
}
@media (max-width: 768px) {
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

.achievement {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 0.25rem 0 2rem 0;
}

.achievement-top {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.achievement-stat {
  font-family: "Montserrat", sans-serif;
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--color-ruby);
  line-height: 1;
  flex-shrink: 0;
}

.achievement-tag {
  font-family: "Montserrat", sans-serif;
  font-size: 0.7rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--color-ruby);
  display: block;
  margin-bottom: 0.35rem;
}

.achievement-title {
  font-family: "Montserrat", sans-serif;
  font-size: 1.15rem;
  font-weight: 700;
  color: var(--color-text-secondary);
  margin: 0;
}

.achievement-desc {
  font-family: "Montserrat", sans-serif;
  font-size: 0.95rem;
  color: var(--color-text-muted);
  line-height: 1.65;
  margin: 0;
}

.divider {
  width: 100%;
  height: 1px;
  background: var(--color-border);
  margin: 0.5rem 0 1.75rem 0;
}
</style>
