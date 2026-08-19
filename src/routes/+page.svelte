<script>
import { base } from "$app/paths";
</script>

<main class="blog-container">
  <section class="blog-title">
    <h2>nicolaileo</h2>
  </section>

  <section class="blog-item">
    <a href="{base}/thoughts" class="blog-link">
      <h2>Thoughts</h2>
      <div class="blog-date">April 2, 2026</div>
      <p>Tech, leadership, and things worth writing down.</p>
    </a>
  </section>

  <section class="blog-item">
    <a href="{base}/skills" class="blog-link">
      <h2>Skills</h2>
      <p>React, Next.js, TypeScript, Node.js.</p>
    </a>
  </section>
  
  <section class="blog-item">
    <a href="{base}/projects" class="blog-link">
      <h2>Projects</h2>
      <p>Work and personal builds.</p>
    </a>
  </section>
  <section class="blog-item">
    <a href="{base}/achievements" class="blog-link">
      <h2>Achievements</h2>
      <p>Numbers behind the work.</p>
    </a>
  </section>
  <section class="blog-item">
    <a href="{base}/career-and-xp" class="blog-link">
      <h2>Career &amp; XP</h2>
      <p>Roles, milestones, and the road so far.</p>
    </a>
  </section>
  <section class="blog-item">
    <a href="{base}/contact-me" class="blog-link">
      <h2>Contact me</h2>
      <p>Be in contact.</p>
    </a>
  </section>
</main>

<style>
.blog-container {
  width: 40vw;
  margin: 2rem auto 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}
@media (max-width: 768px) {
  .blog-container { width: 80vw; }
}

.blog-title {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 2rem;
}

.blog-title h2 {
  width: 100%;
  border-radius: 12px;
  padding: 1.1rem 1.3rem;
  box-sizing: border-box;
  text-align: left;
  margin: 0 0 1rem 0;
  font-size: 1.3rem;
  color: var(--color-text);
}

.blog-item {
  border-radius: 12px;
  padding: 1.1rem 1.3rem;
  width: 100%;
  box-sizing: border-box;
  text-align: left;
  transition: transform 0.38s cubic-bezier(0.22, 0.61, 0.36, 1);
  will-change: transform;
}
.blog-item:hover {
  cursor: pointer;
  transform: scale(1.01);
  z-index: 2;
}

.blog-item h2 {
  margin: 0 0 0.25rem 0;
  font-size: 1.3rem;
  color: var(--color-text-secondary);
  font-family: "Montserrat", sans-serif;
  font-weight: 700;
}
.blog-date {
  font-size: 0.9rem;
  color: var(--color-text-muted);
  font-family: "Montserrat", sans-serif;
}

h1, h2, h3, h4, h5, h6, p {
  font-size: inherit;
  font-family: "Montserrat", sans-serif;
}

p {
  margin: 0;
  color: var(--color-text-muted);
}

.blog-link {
  display: block;
  color: inherit;
  text-decoration: none;
}
.blog-link:hover h2 {
  text-decoration: underline;
}
</style>
