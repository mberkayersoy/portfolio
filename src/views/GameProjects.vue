<template>
  <div class="game-projects-container">
    <div class="header-block">
    </div>
    <div class="projects-list-block">
      <ProjectsList v-bind:projects="projects" :openProjectId="openProjectId" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import ProjectsList from "@/components/ProjectsList.vue";
import gameProjectsData from "@/data/GameProjectsData.ts";

export default Vue.extend({
  name: "GameProjects",
  components: {
    ProjectsList,
  },
  data: function () {
    return {
      projects: gameProjectsData,
    };
  },
  computed: {
    openProjectId(): string | null {
      return this.$route.query.open ? String(this.$route.query.open) : null;
    }
  }
});
</script>

<style scoped>
.game-projects-container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 24px;
  box-sizing: border-box;
}

.header-block {
  text-align: center;
  margin-bottom: 32px;
}

h1 {
  font-size: 2.8em;
  font-weight: 800;
  margin-bottom: 12px;
  color: var(--accent-color);
  letter-spacing: -1px;
}

.subtitle {
  font-size: 1.2em;
  color: var(--text-color);
  opacity: 0.8;
  margin-bottom: 8px;
}

.projects-list-block {
  background: var(--card-bg);
  border-radius: 24px;
  box-shadow: 0 4px 32px rgba(0,0,0,0.07);
  padding: 32px 12px;
}

@media (min-width: 900px) {
  .game-projects-container {
    padding: 48px 32px;
  }
  .projects-list-block {
    padding: 48px 40px;
  }
}
</style>
