<template>
  <div class="other-projects-container">
    <h1>Other stuff</h1>
    <div class="other-desc">And here are some other stuff I've made or heavily contributed to, which are totally different than the stuff from earlier.</div>
    <ProjectsList v-bind:projects="projects" />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import ProjectsList from "@/components/ProjectsList.vue";
import otherProjectsData from "@/data/OtherProjectsData.ts";

export default Vue.extend({
  name: "OtherProjects",
  components: {
    ProjectsList,
  },
  data: function () {
    return {
      projects: otherProjectsData,
    };
  },
});
</script>

<style scoped>
.other-projects-container {
  width: 100%;
  padding: 24px;
  box-sizing: border-box;
}
@media (min-width: 900px) {
  .other-projects-container {
    padding: 48px 32px;
  }
}
.other-desc {
  margin-bottom: 32px;
  font-size: 1.1em;
}
</style>
