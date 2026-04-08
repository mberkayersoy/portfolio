<template>
  <div class="projects-page">
    <header class="page-header">
      <h1>Projects</h1>
      <p class="page-subtitle">Games and interactive experiences I've shipped.</p>
    </header>
    <ProjectsList :projects="projects" :openProjectId="openProjectId" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import ProjectsList from '@/components/ProjectsList.vue';
import gameProjectsData from '@/data/GameProjectsData.ts';

export default Vue.extend({
  name: 'GameProjects',
  components: { ProjectsList },
  data() {
    return { projects: gameProjectsData };
  },
  computed: {
    openProjectId(): string | null {
      return this.$route.query.open ? String(this.$route.query.open) : null;
    },
  },
});
</script>

<style scoped>
.page-header {
  margin-bottom: 40px;
  padding-bottom: 32px;
  border-bottom: 1px solid var(--border);
}

h1 { margin-bottom: 8px; }

.page-subtitle {
  font-size: 0.9rem;
  color: var(--text-muted);
  margin: 0;
}
</style>
