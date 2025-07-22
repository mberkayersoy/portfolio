<template>
  <div id="app">
    
    <link rel="stylesheet" href="@/assets/projects/projects.css" type="text/css">

    <Header>
      <template v-slot:theme-toggle>
        <div class="theme-toggle">
          <button @click="toggleTheme" :title="isDark ? 'Switch to Light Mode' : 'Switch to Dark Mode'">
            <span v-if="isDark">🌙</span>
            <span v-else>☀️</span>
          </button>
        </div>
      </template>
    </Header>
    <div class="main">
      <transition name="fade" mode="out-in">
        <router-view/>
      </transition>
    </div>
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
  components: {
    Header, Footer
  },
  data() {
    return {
      isDark: true
    }
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
      const theme = this.isDark ? 'theme-dark' : 'theme-light';
      document.documentElement.classList.remove('theme-dark', 'theme-light');
      document.documentElement.classList.add(theme);
    }
  }
});

// Preload heavy images or gifs that are used in other pages
Helpers.preloadImages([
  "img/projects/project-1-icon.png",
  "img/projects/project-2-icon.png",
  "img/projects/project-3-icon.png"
]);

</script>

<style lang="less">

@import './css/projects.less';
@import './css/variables.less';

html, body {
  margin: 0px;
  background-color: var(--body-bg);
}

#app {
  background-color: var(--content-bg);
  color: var(--text-color);
  font-family: 'Karla', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 1.1em;
  line-height: 1.6em;
  text-align: justify;
}

.theme-toggle {
  margin-left: 1.5rem;
  display: flex;
  align-items: center;
  button {
    background: var(--card-bg);
    color: var(--accent-color);
    border: 1px solid var(--border-color);
    border-radius: 20px;
    padding: 8px 18px;
    font-size: 1em;
    font-weight: 700;
    cursor: pointer;
    box-shadow: 0 2px 8px rgba(0,0,0,0.04);
    transition: background 0.2s, color 0.2s;
  }
  button:hover {
    background: var(--accent-color);
    color: var(--card-bg);
  }
}

h1, h2, h3, h4, h5 {
  text-align: left;
}

a {
  color: var(--accent-color);
  text-decoration: none;
  opacity: 0.7;
  transition: opacity 0.2s;
}
a:hover, .router-link-exact-active {
  opacity: 1;
}

h1 {
  font-size: 2.5em;
  font-weight: 700;
  margin-top: 0.5em;
  margin-bottom: 40px;
  margin-left: 0;
  line-height: 1.1em;
  letter-spacing: -1px;
}

.main {
    padding: 12px;
  }

@media only screen and (min-width: 620px){
  #app {
    text-align: left;
    line-height: 1.8em;
  }
  h1 {
    margin-top: 0.67em;
    margin-bottom: 80px;
    line-height: 0.7em;
  }
  .main {
    padding: 0px 40px 40px 180px;
  }
  .main, .header, .footer {
    max-width: 1200px;
    margin: 0 auto;
  }
}

.fade-enter-active,
.fade-leave-active {
  transition-duration: 0.2s;
  transition-property: opacity;
  transition-timing-function: ease;
}

.fade-enter,
.fade-leave-active {
  opacity: 0
}

</style>
