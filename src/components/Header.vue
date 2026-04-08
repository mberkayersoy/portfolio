<template>
  <header class="header">
    <div class="header-inner">
      <router-link to="/" class="logo">Berkay Ersoy</router-link>

      <button class="burger" @click="open = !open" :aria-expanded="open.toString()">
        <span /><span /><span />
      </button>

      <nav :class="{ open }">
        <router-link to="/">About</router-link>
        <router-link to="/game-projects">Projects</router-link>
        <router-link to="/resume">Resume</router-link>
        <router-link to="/contact">Contact</router-link>
        <slot name="theme-toggle" />
      </nav>
    </div>
  </header>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'Header',
  data() { return { open: false }; },
  watch: { $route() { this.open = false; } },
});
</script>

<style scoped lang="less">
@import '../css/variables.less';

.header {
  position: sticky;
  top: 0;
  z-index: 100;
  background: var(--bg);
  border-bottom: 1px solid var(--border);
}

.header-inner {
  max-width: 860px;
  margin: 0 auto;
  padding: 0 24px;
  height: 56px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

/* Logo */
.logo {
  font-family: 'Syne', sans-serif;
  font-weight: 800;
  font-size: 0.95rem;
  letter-spacing: 0.04em;
  color: var(--text);
  text-decoration: none;
}
.logo:hover { text-decoration: none; }

/* Nav links */
nav {
  display: flex;
  align-items: center;
  gap: 2px;

  a {
    font-size: 0.78rem;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    font-weight: 500;
    color: var(--text-muted);
    text-decoration: none;
    padding: 6px 10px;
    border-radius: 4px;
    transition: color 0.15s;
  }
  a:hover,
  a.router-link-exact-active {
    color: var(--text);
    text-decoration: none;
  }
}

/* Burger */
.burger {
  display: none;
  flex-direction: column;
  justify-content: center;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;

  span {
    display: block;
    width: 22px;
    height: 1.5px;
    background: var(--text);
    transition: opacity 0.2s;
  }
}

/* Mobile */
@media (max-width: 680px) {
  .burger { display: flex; }

  nav {
    display: none;
    position: absolute;
    top: 56px;
    left: 0;
    right: 0;
    background: var(--bg);
    border-bottom: 1px solid var(--border);
    flex-direction: column;
    align-items: flex-start;
    padding: 16px 24px 20px;
    gap: 4px;

    a {
      width: 100%;
      font-size: 0.9rem;
      padding: 10px 0;
    }

    &.open { display: flex; }
  }
}
</style>
