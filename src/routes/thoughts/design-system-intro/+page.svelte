<script>
import { base } from "$app/paths";
import Seo from "$lib/components/Seo.svelte";
</script>

<Seo
  title="Getting started with system design"
  description="System design is ten skills wearing a trench coat. Notes on learning caching, queues, and message brokers by drawing, breaking things, and starting from client talks to server."
  path="/thoughts/design-system-intro"
  image="/thoughts/design-system-intro.png"
  type="article"
/>

<main class="detail-container">
  <a href="{base}/thoughts" class="back-link">
    <svg class="back-icon" viewBox="0 0 640 640" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <path d="M169.4 297.4C156.9 309.9 156.9 330.2 169.4 342.7L361.4 534.7C373.9 547.2 394.2 547.2 406.7 534.7C419.2 522.2 419.2 501.9 406.7 489.4L237.3 320L406.6 150.6C419.1 138.1 419.1 117.8 406.6 105.3C394.1 92.8 373.8 92.8 361.3 105.3L169.3 297.3z"/>
    </svg>
    back
  </a>

  <span class="post-tag">System Design</span>
  <h1 class="post-title">Getting started with system design</h1>
  <p class="post-date">August 29, 2026</p>

  <p class="post-body">Okay so, system design. Everyone talks about it like it's one skill you either have or you don't. It's not. It's like ten skills wearing a trench coat, networking, databases, caching, queues, message brokers, and every single resource assumes you already know the other nine before they'll explain the tenth. First week in, I mostly just felt behind.</p>

  <figure class="post-image">
    <img src="{base}/thoughts/design-system-intro.png" alt="System design overview: client, CDN, load balancer, API gateway, service layer, cache, database, and workers connected through a message queue" />
    <figcaption>The basic system I sketched out first, before trying to adapt it to anything real.</figcaption>
  </figure>

  <p class="post-body">So here's what I'm actually doing about it: reading a lot, breaking things on purpose, figuring out what a load balancer is really deciding when it routes a request, why Kafka exists, what people mean when they say "scale the database" like it's one simple move. There are a thousand rabbit holes here and I've fallen down most of them. The one rule that's kept me sane: don't skip ahead. Client talks to server, server talks to database. That's the whole system, at the bottom of everything. Every fancy piece gets bolted on later, and only once you know why.</p>

  <p class="post-body">Because that's the part nobody says out loud, every tool in this space exists to fix a specific kind of pain. A cache isn't there to make your architecture diagram look impressive, it shows up when your database is begging for mercy. A queue isn't a box you draw because interviews expect one, it's what you reach for when two services need to talk without holding hands the whole time. Learn the pain first and the tool stops being a random vocabulary word.</p>

  <figure class="post-image">
    <img src="{base}/thoughts/system-design-tools.png" alt="Grid of logos for tools commonly used in system design: Redis, Apache Kafka, RabbitMQ, PostgreSQL, MongoDB, AWS, Google Cloud, Azure, Cloudflare, Elasticsearch, Stripe, SendGrid, Docker, Kubernetes, Nginx, and Datadog" />
    <figcaption>Some of the names that keep showing up once you start pulling on this thread.</figcaption>
  </figure>

  <p class="post-body">There's no magic formula here, no five-step framework that unlocks it. What I actually did was just start drawing. Grabbed <a class="post-link" href="https://excalidraw.com" target="_blank" rel="noopener noreferrer">Excalidraw</a> and tried to fit in everything that could possibly be involved in a generic system, straight out of my head, no real requirements, just every piece I could think of and the different ways each one could be handled. Once that mess existed on screen, the real work started: poking holes in it and filling gaps one tool at a time. Prepping for a payment service interview? Go find out what payment providers actually exist and how they'd bolt on. Need file storage? Same move, go see what's out there. You're never going to memorize every tool on the market, and you don't need to, you just need the basics solid enough that learning tool number forty-seven takes an afternoon instead of a full identity crisis.</p>

  <p class="post-body">Going back to the theory kept saving me too, it's the only thing that turns a pile of random tools into an actual map instead of scattered trivia. And the cheat code nobody mentions: look at whatever system you already work on every day. Ask why it's built the way it is. Ask, honestly, if it should be.</p>

  <p class="post-body">Here's the part nobody puts in the intro paragraph, though: this doesn't end. There's no boss fight, no certificate, no morning where you wake up and it all just clicks and stays clicked. There's only more scale, more edge cases, more three a.m. pages you never saw coming. Next up for me is scalability, for real this time, less reading, more building things that actually break in my hands. Because that's kind of the whole deal with this stuff. You don't finish system design. You just get better at being a little overwhelmed, permanently, and somehow that starts to feel like progress.</p>
  <p class="post-body"><a href="https://dev.to/codenicolai/getting-started-with-system-design-1kj7" target="_blank" rel="noopener noreferrer" class="post-link">Read the original post →</a></p>
</main>

<style>
.detail-container {
  width: 40vw;
  margin: 2rem auto 5rem auto;
  display: flex;
  flex-direction: column;
  gap: 1.15rem;
}
@media (max-width: 768px) { .detail-container { width: 88vw; } }

.back-link { display: inline-flex; align-items: center; gap: 0.4rem; font-family: "Montserrat", sans-serif; font-size: 0.82rem; font-weight: 600; color: var(--color-text-muted); text-decoration: none; padding: 0.38rem 0.85rem 0.38rem 0.6rem; border-radius: 999px; border: 1px solid var(--color-border); background: transparent; transition: color 0.2s, border-color 0.2s, background 0.2s; margin-bottom: 0.5rem; align-self: flex-start; }
.back-link:hover {
  color: var(--color-text);
  border-color: var(--color-border);
  background: var(--color-tag-bg);
}
.back-icon { width: 12px; height: 12px; fill: currentColor; flex-shrink: 0; }

.post-tag {
  font-family: "Montserrat", sans-serif;
  font-size: 0.7rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--color-sapphire);
}

.post-title {
  font-family: "Montserrat", sans-serif;
  font-size: 1.9rem;
  font-weight: 700;
  margin: 0;
  line-height: 1.3;
  color: var(--color-text);
}

.post-date {
  font-family: "Montserrat", sans-serif;
  font-size: 0.8rem;
  color: var(--color-text-muted);
  margin: -0.4rem 0 0.8rem 0;
}

.post-link {
  color: var(--color-sapphire);
  font-weight: 600;
  text-decoration: none;
}
.post-link:hover {
  text-decoration: underline;
}

.post-body {
  font-family: "Montserrat", sans-serif;
  font-size: 0.97rem;
  color: var(--color-text-secondary);
  line-height: 1.85;
  margin: 0;
}

.post-image {
  margin: 0.5rem 0;
  display: flex;
  flex-direction: column;
  gap: 0.6rem;
}
.post-image img {
  width: 100%;
  border-radius: 10px;
  border: 1px solid var(--color-border);
  background: #fff;
}
.post-image figcaption {
  font-family: "Montserrat", sans-serif;
  font-size: 0.82rem;
  color: var(--color-text-muted);
  text-align: center;
}

code {
  font-family: "Courier New", monospace;
  font-size: 0.88em;
  background: var(--color-tag-bg);
  color: var(--color-tag-text);
  padding: 0.1em 0.4em;
  border-radius: 4px;
}
</style>
