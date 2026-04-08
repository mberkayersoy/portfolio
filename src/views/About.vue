<template>
  <div class="about">

    <!-- Hero -->
    <section class="hero">
      <div class="hero-text">
        <h1>Berkay Ersoy</h1>
        <p class="role">Game Developer</p>
        <p class="bio">
          Computer Engineering graduate specialising in Unity and C#. I design
          and build mobile games — from game architecture and AI mechanics to
          smooth animations and live analytics. My games have reached over
          <strong>160K downloads</strong> on Google Play and the App Store.
        </p>
        <p class="bio">
          I thrive in collaborative environments and I'm currently looking for
          new opportunities to bring engaging, high-quality experiences to
          players.
        </p>
        <p class="contact-line">
          <a href="mailto:mberkayersoy@gmail.com">mberkayersoy@gmail.com</a>
          &nbsp;·&nbsp;
          <router-link to="/contact">Contact</router-link>
        </p>
      </div>
      <div class="hero-photo">
        <img src="img/aboutmeavatar.png" alt="Berkay Ersoy" />
      </div>
    </section>

    <!-- Quick stats -->
    <section class="stats">
      <div class="stat">
        <span class="stat-value">160K+</span>
        <span class="stat-label">Downloads</span>
      </div>
      <div class="stat">
        <span class="stat-value">6+</span>
        <span class="stat-label">Shipped games</span>
      </div>
      <div class="stat">
        <span class="stat-value">4</span>
        <span class="stat-label">Years of experience</span>
      </div>
    </section>

  </div>
</template>

<style scoped>
/* ── Hero ───────────────────────────────────────── */
.hero {
  display: flex;
  flex-direction: column-reverse;
  gap: 40px;
  padding-bottom: 56px;
  border-bottom: 1px solid var(--border);
}

.hero-text h1 {
  margin-bottom: 6px;
}

.role {
  font-size: 0.85rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--text-muted);
  margin: 0 0 28px;
}

.bio {
  font-size: 1rem;
  color: var(--text);
  line-height: 1.75;
  margin-bottom: 14px;
}

.contact-line {
  margin-top: 24px;
  font-size: 0.85rem;
  color: var(--text-muted);

  a {
    color: var(--text-muted);
    text-underline-offset: 3px;
  }
  a:hover { color: var(--text); }
}

.hero-photo img {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  object-fit: cover;
  border: 1px solid var(--border);
  display: block;
}

/* ── Stats ──────────────────────────────────────── */
.stats {
  display: flex;
  gap: 48px;
  padding-top: 48px;
  flex-wrap: wrap;
}

.stat {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.stat-value {
  font-family: 'Syne', sans-serif;
  font-size: 2rem;
  font-weight: 700;
  color: var(--text);
  line-height: 1;
}

.stat-label {
  font-size: 0.75rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--text-muted);
}

/* ── Desktop ────────────────────────────────────── */
@media (min-width: 640px) {
  .hero {
    flex-direction: row;
    align-items: flex-start;
    gap: 56px;
  }

  .hero-text { flex: 1; }

  .hero-photo {
    flex-shrink: 0;
    padding-top: 8px;

    img {
      width: 160px;
      height: 160px;
    }
  }
}
</style>
