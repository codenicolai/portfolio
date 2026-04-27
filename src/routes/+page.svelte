<main class="blog-container">
  <section class="blog-title">
    <h2>nicolaileo</h2>
  </section>

  <section class="blog-item">
    <a href="/posts-and-thoughts" class="blog-link">
      <h2>Posts and Thoughts</h2>
      <div class="blog-date">January 18, 2026</div>
      <p>Formats over apps.</p>
    </a>
  </section>
  <section class="blog-item">
    <a href="/skills" class="blog-link">
      <h2>Skills</h2>
      <div class="blog-date">January 18, 2026</div>
      <p>6+ years shipping products.</p>
    </a>
  </section>
  <section class="blog-item">
    <a href="/my-portfolio" class="blog-link">
      <h2>My Portfolio</h2>
      <div class="blog-date">December 19, 2025</div>
      <p>My new hobby project.</p>
    </a>
  </section>
  <section class="blog-item">
    <a href="/side-projects" class="blog-link">
      <h2>Side projects</h2>
      <div class="blog-date">November 11, 2025</div>
      <p>I'm looking for a new job.</p>
    </a>
  </section>
  <section class="blog-item">
    <a href="/events-and-workshops" class="blog-link">
      <h2>Events and Workshops</h2>
      <div class="blog-date">October 21, 2025</div>
      <p>The joys of vibecoding.</p>
    </a>
  </section>
  <section class="blog-item">
    <a href="/contact-me" class="blog-link">
      <h2>Contact me</h2>
      <div class="blog-date">October 2, 2025</div>
      <p>From handles to hosting.</p>
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
  background: linear-gradient(90deg, #8028f3 0%, #918dfc 30%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  color: transparent;
}

.blog-item {
  border-radius: 12px;
  padding: 1.1rem 1.3rem;
  width: 100%;
  box-sizing: border-box;
  text-align: left;
  transition: transform 0.38s cubic-bezier(0.22, 0.61, 0.36, 1), background 0.2s;
  will-change: transform;
}
.blog-item:hover {
  cursor: pointer;
  transform: scale(1.01) translateY(0);
  background: var(--color-item-hover);
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
