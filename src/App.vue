<template>
  <div id="app">
    <Header>
      <template v-slot:theme-toggle>
        <button class="theme-btn" @click="toggleTheme" :title="isDark ? 'Switch to light mode' : 'Switch to dark mode'">
          <i :class="isDark ? 'fa fa-sun-o' : 'fa fa-moon-o'" />
        </button>
      </template>
    </Header>

    <main class="main">
      <transition name="fade" mode="out-in">
        <router-view />
      </transition>
    </main>

    <Footer />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Helpers from './helpers';

export default Vue.extend({
  name: 'App',
  components: { Header, Footer },
  data() {
    return { isDark: true };
  },
  mounted() {
    this.applyTheme();
  },
  methods: {
    toggleTheme() {
      this.isDark = !this.isDark;
      this.applyTheme();
    },
    applyTheme() {
      document.documentElement.classList.toggle('theme-dark', this.isDark);
      document.documentElement.classList.toggle('theme-light', !this.isDark);
    },
  },
});

Helpers.preloadImages([
  'img/projects/project-1-icon.png',
  'img/projects/project-2-icon.png',
  'img/projects/project-3-icon.png',
]);
</script>

<style lang="less">
@import './css/variables.less';

/* ── Reset & base ──────────────────────────────────────── */
*, *::before, *::after { box-sizing: border-box; }

html, body {
  margin: 0;
  padding: 0;
  background: var(--bg);
}

#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  background: var(--bg);
  color: var(--text);
  font-family: 'Inter', system-ui, sans-serif;
  font-weight: 400;
  font-size: 15px;
  line-height: 1.7;
  -webkit-font-smoothing: antialiased;
}

/* ── Typography ───────────────────────────────────────── */
h1, h2, h3, h4, h5, h6 {
  font-family: 'Syne', sans-serif;
  font-weight: 700;
  line-height: 1.15;
  margin: 0;
  color: var(--text);
}

h1 { font-size: 2.6rem; letter-spacing: -0.03em; }
h2 { font-size: 0.72rem; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase; color: var(--text-muted); }
h3 { font-size: 1rem; font-weight: 700; }
h4 { font-size: 0.85rem; font-weight: 400; color: var(--text-muted); }
h5 { font-size: 0.9rem; font-weight: 600; }

p { margin: 0 0 1em; }

a {
  color: var(--text);
  text-decoration: underline;
  text-decoration-color: var(--border);
  text-underline-offset: 3px;
  transition: text-decoration-color 0.15s;
}
a:hover { text-decoration-color: var(--text); }

ul { padding-left: 1.25em; }
li { margin-bottom: 0.3em; }

/* ── Layout ───────────────────────────────────────────── */
.main {
  flex: 1;
  width: 100%;
  max-width: 860px;
  margin: 0 auto;
  padding: 56px 24px 80px;
}

/* ── Theme toggle button ──────────────────────────────── */
.theme-btn {
  background: none;
  border: 1px solid var(--border);
  width: 30px;
  height: 30px;
  padding: 0;
  border-radius: 4px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.95rem;
  transition: border-color 0.15s;

  /* sun → yellow */
  .fa-sun-o  { color: #f5c542; }
  /* moon → silver-blue */
  .fa-moon-o { color: #a8b8d0; }
}
.theme-btn:hover { border-color: var(--text); }

/* ── Page transitions ─────────────────────────────────── */
.fade-enter-active,
.fade-leave-active { transition: opacity 0.18s ease; }
.fade-enter, .fade-leave-active { opacity: 0; }

/* ── Dialog v-html content ────────────────────────────── */
/* These must be global because v-html bypasses scoped CSS  */
.dialog-content {
  img {
    max-width: 100%;
    height: auto;
    display: block;
  }

  .phone-screenshot {
    width: 140px;
    margin: 8px;
    border-radius: 4px;
    display: inline-block;
    vertical-align: top;
  }

  .pc-screenshot {
    width: 100%;
    max-width: 480px;
    margin: 8px 0;
    border-radius: 4px;
  }

  .paragraph {
    margin: 16px 0;
  }

  .center {
    text-align: center;
  }

  iframe.youtube {
    width: 100%;
    aspect-ratio: 16/9;
    border: none;
    border-radius: 4px;
    margin: 8px 0;
  }

  .notice {
    border: 1px solid var(--border);
    background: var(--surface);
    padding: 10px 14px;
    border-radius: 4px;
    font-size: 0.85rem;
  }

  a {
    color: var(--text-muted);
    text-decoration: underline;
    text-underline-offset: 3px;
    &:hover { color: var(--text); }
  }

  /* store badge images */
  img[src*="play-store-logo"],
  img[src*="app-store-logo"],
  img[src*="ms-store-logo"] {
    width: 120px;
    display: inline-block;
    margin: 6px 8px;
  }
}
</style>
