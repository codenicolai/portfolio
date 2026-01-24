<nav class="navbar">
  <a class="navbar-avatar" href="https://github.com/codenicolai" target="_blank" rel="noopener noreferrer" title="nicolai on GitHub">
    <img src="/src/lib/assets/avatar.png" alt="Avatar" />
  </a>
</nav>

<main class="blog-container">
  <section class="blog-title"> <h2>nicolaileo</h2></section>
   
   <section class="blog-item">
    <h2>Posts and Tougths</h2>
    <div class="blog-date">January 18, 2026</div>
    <p>Formats over apps.</p>
  </section>
  <section class="blog-item">
    <h2>Skills</h2>
    <div class="blog-date">January 18, 2026</div>
    <p>Formats over apps.</p>
  </section>
  <section class="blog-item">
    <h2>My Portfolio</h2>
    <div class="blog-date">December 19, 2025</div>
    <p>My new hobby project.</p>
  </section>
  <section class="blog-item">
    <h2>Side projects</h2>
    <div class="blog-date">November 11, 2025</div>
    <p>I'm looking for a new job.</p>
  </section>
  <section class="blog-item">
    <h2>Events and Workshops</h2>
    <div class="blog-date">October 21, 2025</div>
    <p>The joys of vibecoding.</p>
  </section>
  <section class="blog-item">
    <h2>Contact me</h2>
    <div class="blog-date">October 2, 2025</div>
    <p>From handles to hosting.</p>
  </section>
</main>

<style>
.navbar {
  width: 100%;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 1rem 2rem 0 2rem;
  box-sizing: border-box;
}
.navbar-avatar {
  width: 44px;
  height: 44px;
  border-radius: 50%;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #fff;
  box-shadow: 0 2px 8px rgba(0,0,0,0.04);
  cursor: pointer;
  text-decoration: none;
}
.navbar-avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
  display: block;
}
.blog-container {
  width: 40vw;
  margin: 2rem auto 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}
@media (max-width: 768px) {
  .blog-container {
    width: 80vw;
  }
}

.blog-title{
width: 100%;
display: flex;
justify-content: center;
align-items: center;
margin-bottom: 2rem;
}

.blog-title h2 {
  width: 100%;
  margin-top: -5rem;
  border-radius: 12px;
  padding: 1.1rem 1.3rem;
  box-sizing: border-box;
  text-align: left;
  margin-bottom: 1rem;
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
  transition: transform 0.38s cubic-bezier(0.22, 0.61, 0.36, 1);
  will-change: transform;
}
.blog-item:hover {
  cursor: pointer;
  transform: scale(1.01) translateY(0);
  z-index: 2;
}

.blog-item h2 {
  margin: 0 0 0.25rem 0;
  font-size: 1.3rem;
  color: #454545;
  font-family: "Montserrat", sans-serif;
  font-weight: 700;
  font-style: normal;
}
.blog-date {
  font-size: 0.9rem;
  color: #888;
  font-family: "Montserrat", sans-serif;
}

h1, h2, h3, h4, h5, h6, p {
font-size: inherit; /* Ensure headings are smaller */
font-family: "Montserrat", sans-serif;
}

p {
    margin: 0;
}
</style>
