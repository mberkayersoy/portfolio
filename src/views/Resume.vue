<template>
  <div class="resume">

    <!-- Summary + photo -->
    <section class="summary-row">
      <div class="summary-text">
        <h2>Summary</h2>
        <p>
          Throughout my academic journey in Computer Engineering I actively
          engaged in various projects. My passion for game development led me to
          explore different technologies before gaining professional experience,
          and over time I transitioned into the industry.
        </p>
        <p>
          I worked as a Game Developer at Purple Owl Interactive, leading
          Unity-based mobile games from concept to launch. Those games
          collectively reached <strong>160K+ downloads</strong> on Google Play
          and the App Store. Before that, I worked at E-Moli Interactive on AR
          games and real-time multiplayer. I also gained experience through
          internships at Udo Games and Skyloft.
        </p>
        <p>
          Outside work I enjoy video games, comic books, cooking and
          skateboarding. I'm always eager to learn new technologies.
        </p>
      </div>
      <div class="summary-photo">
        <img src="img/Resume_photo.png" alt="Berkay Ersoy" />
      </div>
    </section>

    <!-- Work Experience -->
    <section class="resume-section">
      <h2>Work Experience</h2>

      <div class="job">
        <div class="job-header">
          <div>
            <h3>Purple Owl Interactive</h3>
            <span class="job-title">Game Developer · Vancouver, Canada (Remote)</span>
          </div>
          <span class="job-date">Jul 2024 – Mar 2025</span>
        </div>
        <p class="job-intro">
          Developed three Unity-based mobile games published on Google Play and
          the App Store, collectively reaching 160K+ downloads.
        </p>

        <div class="project-entry">
          <h5>Solitaire</h5>
          <ul>
            <li>Classic Klondike Solitaire with smooth animations and an intelligent hint system.</li>
            <li>Every deal is guaranteed solvable via a custom shuffling algorithm.</li>
            <li>Achieved 50K+ downloads on Google Play.</li>
            <li>
              <a href="https://play.google.com/store/apps/details?id=com.purpleowl.solitaire&hl=tr" target="_blank" rel="noopener">Google Play</a>
              ·
              <a href="https://apps.apple.com/tr/app/solitaire-classic-card-game/id6740050961?l=tr" target="_blank" rel="noopener">App Store</a>
            </li>
          </ul>
        </div>

        <div class="project-entry">
          <h5>Gin Rummy</h5>
          <ul>
            <li>Competitive card game with AI opponents and multiplayer modes.</li>
            <li>Intuitive UI and polished gameplay mechanics.</li>
            <li>Achieved 100K+ downloads on Google Play.</li>
            <li>
              <a href="https://play.google.com/store/apps/details?id=com.purpleowl.gin.rummy.card&hl=tr" target="_blank" rel="noopener">Google Play</a>
              ·
              <a href="https://apps.apple.com/tr/app/gin-rummy-card-game/id6740112194?l=tr" target="_blank" rel="noopener">App Store</a>
            </li>
          </ul>
        </div>

        <div class="project-entry">
          <h5>Yatzy</h5>
          <ul>
            <li>Feature-rich dice game with multiple game modes and fair AI mechanics.</li>
            <li>Achieved 10K+ downloads on Google Play.</li>
            <li>
              <a href="https://play.google.com/store/apps/details?id=com.purpleowl.yatzy.dice.game&hl=tr" target="_blank" rel="noopener">Google Play</a>
              ·
              <a href="https://apps.apple.com/tr/app/yatzyclassic/id6740508341?l=tr" target="_blank" rel="noopener">App Store</a>
            </li>
          </ul>
        </div>
      </div>

      <div class="job">
        <div class="job-header">
          <div>
            <h3>E-Moli Interactive</h3>
            <span class="job-title">Game Developer · Eskişehir, Turkey (Remote)</span>
          </div>
          <span class="job-date">Feb 2024 – May 2024</span>
        </div>
        <p>
          Developed four Unity projects from the ground up — three single-player
          experiences and one LAN multiplayer game using Mirror Networking.
          <router-link to="/game-projects?open=wall-Games">View projects →</router-link>
        </p>
      </div>

      <div class="job">
        <div class="job-header">
          <div>
            <h3>Udo Games</h3>
            <span class="job-title">Game Developer Intern · Ankara, Turkey (Remote)</span>
          </div>
          <span class="job-date">Jul 2023 – Aug 2023</span>
        </div>
        <p>
          Hands-on training across game development, art, marketing and HR.
          Participated in an end-of-internship game jam.
          Source code available on
          <a href="https://github.com/mberkayersoy/MowIt" target="_blank" rel="noopener">GitHub</a>.
        </p>
      </div>

      <div class="job">
        <div class="job-header">
          <div>
            <h3>Skyloft</h3>
            <span class="job-title">Game Developer Intern · Izmir, Turkey (On-site)</span>
          </div>
          <span class="job-date">Aug 2022 – Sep 2022</span>
        </div>
        <p>
          Focused on gameplay mechanics, UI design, and game performance
          optimisation. Built a 3D Calculator educational game using infix/postfix
          expression algorithms.
        </p>
      </div>
    </section>

    <!-- Skills -->
    <section class="resume-section">
      <h2>Skills</h2>
      <div class="skills-grid">
        <div class="skill-group">
          <h4>Languages</h4>
          <div class="tags">
            <SkillRate name="C#" />
            <SkillRate name="C++" />
            <SkillRate name="Python" />
            <SkillRate name="Java" />
            <SkillRate name="SQL" />
          </div>
        </div>
        <div class="skill-group">
          <h4>Tools & Frameworks</h4>
          <div class="tags">
            <SkillRate name="Unity" />
            <SkillRate name="Zenject" />
            <SkillRate name="UniTask" />
            <SkillRate name="Firebase" />
            <SkillRate name="Photon Engine" />
            <SkillRate name="Mirror Networking" />
            <SkillRate name="Git" />
          </div>
        </div>
        <div class="skill-group">
          <h4>Technical</h4>
          <div class="tags">
            <SkillRate name="Design Patterns" />
            <SkillRate name="Game Architecture" />
            <SkillRate name="Game Physics" />
          </div>
        </div>
        <div class="skill-group">
          <h4>Soft Skills</h4>
          <div class="tags">
            <SkillRate name="Teamwork" />
            <SkillRate name="Continuous Learning" />
            <SkillRate name="Time Management" />
            <SkillRate name="Creativity" />
          </div>
        </div>
      </div>
    </section>

    <!-- Education -->
    <section class="resume-section">
      <h2>Education</h2>
      <div class="job">
        <div class="job-header">
          <div>
            <h3>Mugla Sitki Kocman University</h3>
            <span class="job-title">B.S. in Computer Engineering</span>
          </div>
          <span class="job-date">Sep 2018 – Jun 2023</span>
        </div>
      </div>
    </section>

    <!-- Languages -->
    <section class="resume-section">
      <h2>Languages</h2>
      <div class="lang-row">
        <span>English <span class="lang-level">B2</span></span>
        <span>Turkish <span class="lang-level">Native</span></span>
      </div>
    </section>

    <!-- Interests -->
    <section class="resume-section">
      <h2>Interests</h2>
      <p>
        I play drums and guitar — I've performed live on stage with a band and
        enjoy street sessions. I'm also into skateboarding, Latin dances and
        basketball.
      </p>
    </section>

  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import SkillRate from '@/components/SkillRate.vue';

export default Vue.extend({
  name: 'Resume',
  components: { SkillRate },
});
</script>

<style scoped>
/* ── Section wrapper ─────────────────────────────── */
.resume-section {
  padding: 48px 0 0;
  border-top: 1px solid var(--border);
  margin-top: 48px;

  > h2 {
    font-size: 0.95rem;
    letter-spacing: 0.1em;
    margin-bottom: 32px;
  }
}

/* ── Summary row ─────────────────────────────────── */
.summary-row {
  display: flex;
  flex-direction: column;
  gap: 32px;
  padding-bottom: 0;

  p { color: var(--text); line-height: 1.75; }
  h2 { font-size: 0.95rem; letter-spacing: 0.1em; }
  h2 { margin-bottom: 20px; }
}

.summary-photo img {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  object-fit: cover;
  border: 1px solid var(--border);
}

@media (min-width: 640px) {
  .summary-row {
    flex-direction: row;
    align-items: flex-start;
    gap: 48px;
  }
  .summary-row > .summary-text { flex: 1; }
  .summary-photo { flex-shrink: 0; padding-top: 42px; }
}

/* ── Job entries ─────────────────────────────────── */
.job {
  margin-bottom: 40px;

  &:last-child { margin-bottom: 0; }
}

.job-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 16px;
  margin-bottom: 12px;
  flex-wrap: wrap;

  h3 { margin-bottom: 2px; }
}

.job-title {
  font-size: 0.82rem;
  color: var(--text-muted);
}

.job-date {
  font-size: 0.78rem;
  color: var(--text-muted);
  white-space: nowrap;
  flex-shrink: 0;
  padding-top: 3px;
}

.job-intro { margin-bottom: 16px; color: var(--text); }

.project-entry {
  margin: 16px 0;
  padding-left: 16px;
  border-left: 2px solid var(--border);

  h5 { margin-bottom: 6px; color: var(--text); }
  ul { margin: 0; color: var(--text); }
  li { font-size: 0.9rem; line-height: 1.6; }
}

/* ── Skills ──────────────────────────────────────── */
.skills-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 32px 48px;
}

.skill-group h4 {
  font-size: 0.72rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--text-muted);
  margin-bottom: 12px;
  font-weight: 600;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

/* ── Languages ───────────────────────────────────── */
.lang-row {
  display: flex;
  gap: 32px;
  font-size: 0.9rem;
  color: var(--text);
}

.lang-level {
  font-size: 0.75rem;
  color: var(--text-muted);
  margin-left: 6px;
  text-transform: uppercase;
  letter-spacing: 0.06em;
}

@media (max-width: 480px) {
  .skills-grid { grid-template-columns: 1fr; gap: 24px; }
}
</style>
