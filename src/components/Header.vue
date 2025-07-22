<template>
  <header class="header">
    <nav class="nav-bar">
      <div class="logo">BERKAY ERSOY</div>
      <button class="menu-toggle" @click="menuOpen = !menuOpen">
        <span v-if="!menuOpen">☰</span>
        <span v-else>✕</span>
      </button>
      <ul :class="{ open: menuOpen }">
        <li><router-link to="/">About me</router-link></li>
        <li><router-link to="/game-projects">Projects</router-link></li>
        <!-- <li><router-link to="/other-projects">Other stuff</router-link></li> -->
        <li><router-link to="/resume">Resume</router-link></li>
        <li><router-link to="/contact">Contact</router-link></li>
        <li class="theme-toggle-slot">
          <slot name="theme-toggle"></slot>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Header",
  data() {
    return {
      menuOpen: false
    }
  },
  watch: {
    $route() {
      this.menuOpen = false;
    }
  }
});
</script>

<style scoped lang="less">
@import '../css/variables.less';

.header {
  width: 100%;
  position: sticky;
  top: 0;
  z-index: 100;
  background: var(--header-bg);
  box-shadow: 0 2px 12px rgba(0,0,0,0.04);
}

.nav-bar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 1.5rem;
  min-height: 64px;
}

.logo {
  font-weight: 900;
  font-size: 1.2em;
  letter-spacing: 2px;
  color: var(--accent-color);
  text-transform: uppercase;
}

.menu-toggle {
  display: none;
  background: none;
  border: none;
  font-size: 2em;
  color: var(--accent-color);
  cursor: pointer;
}

ul {
  display: flex;
  gap: 1.5rem;
  list-style: none;
  margin: 0;
  padding: 0;
  align-items: center;
}

li {
  display: flex;
}

.theme-toggle-slot {
  margin-left: 1.5rem;
  display: flex;
  align-items: center;
}

a {
  text-transform: uppercase;
  padding: 8px 16px;
  border-radius: 8px;
  font-weight: 700;
  color: var(--text-color);
  transition: background 0.2s, color 0.2s;
  font-size: 1em;
}
a.router-link-exact-active, a:hover {
  background: var(--accent-color);
  color: var(--card-bg);
}

@media (max-width: 900px) {
  .nav-bar {
    padding: 0 0.5rem;
  }
  .logo {
    font-size: 1em;
  }
  ul {
    gap: 0.5rem;
  }
}

@media (max-width: 700px) {
  .menu-toggle {
    display: block;
  }
  ul {
    position: absolute;
    top: 64px;
    right: 0;
    left: 0;
    background: var(--header-bg);
    flex-direction: column;
    align-items: flex-start;
    padding: 1rem 2rem;
    gap: 1rem;
    box-shadow: 0 8px 24px rgba(0,0,0,0.08);
    display: none;
  }
  ul.open {
    display: flex;
  }
  li {
    width: 100%;
  }
  .theme-toggle-slot {
    margin-left: 0;
    width: 100%;
    justify-content: flex-start;
    margin-top: 8px;
  }
  a {
    width: 100%;
    text-align: left;
    font-size: 1.1em;
    padding: 12px 0;
  }
}
</style>
