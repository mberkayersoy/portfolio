<template>
  <div>
    <div class="projects-grid">
      <div
        v-for="project in projects"
        :key="project.id"
        class="project-card"
        :class="{ wide: project.isWide, high: project.isHigh }"
        @click="showDetails(project)"
      >
        <div
          class="card-image"
          :style="{ backgroundImage: 'url(' + project.iconUrl + ')' }"
        />
        <div class="card-label">
          <span class="card-name">{{ project.name }}</span>
          <span class="card-arrow">→</span>
        </div>
      </div>
    </div>

    <ProjectDetailsOverlay
      :visible="showPopup"
      :title="popupTitle"
      :htmlContent="popupContent"
      :color="popupColor"
      @close="showPopup = false"
    />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import ProjectDetailsOverlay from '@/components/ProjectDetailsOverlay.vue';
import ProjectData from '@/data/ProjectData.ts';

export default Vue.extend({
  name: 'ProjectsList',
  components: { ProjectDetailsOverlay },
  props: {
    projects: Array,
    openProjectId: { type: String, default: null },
  },
  data() {
    return {
      showPopup: false,
      popupTitle: '',
      popupColor: '',
      popupContent: '',
    };
  },
  watch: {
    openProjectId: {
      immediate: true,
      handler(val) {
        if (val && this.projects) {
          const p = this.projects.find((p: any) => p.id === val || p.name === val);
          if (p) this.showDetails(p as ProjectData);
        }
      },
    },
  },
  methods: {
    showDetails(item: ProjectData) {
      this.popupTitle = item.name;
      this.popupColor = item.accentColor;
      this.popupContent = item.htmlDescription;
      this.showPopup = true;
      window.scrollTo(0, 0);
    },
  },
});
</script>

<style scoped>
/* ── Grid ─────────────────────────────────────── */
.projects-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 12px;
}

@media (min-width: 560px) {
  .projects-grid {
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: 220px;
  }
  .wide {
    grid-column: span 3;
    grid-row: span 2;
  }
  .high {
    grid-row: span 2;
  }
}

/* ── Card ─────────────────────────────────────── */
.project-card {
  position: relative;
  overflow: hidden;
  cursor: pointer;
  border-radius: 6px;
  background: var(--surface);
  min-height: 200px;
}

.card-image {
  position: absolute;
  inset: 0;
  background-size: cover;
  background-position: center;
  transition: transform 0.35s ease;
}

.project-card:hover .card-image {
  transform: scale(1.04);
}

/* Gradient overlay */
.project-card::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(0,0,0,0.72) 0%, transparent 55%);
  pointer-events: none;
}

/* Label */
.card-label {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 1;
  padding: 14px 16px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.card-name {
  font-family: 'Syne', sans-serif;
  font-size: 0.9rem;
  font-weight: 700;
  color: #fff;
  letter-spacing: 0.02em;
}

.card-arrow {
  font-size: 0.9rem;
  color: rgba(255,255,255,0.5);
  transition: color 0.2s, transform 0.2s;
}

.project-card:hover .card-arrow {
  color: #fff;
  transform: translateX(3px);
}
</style>
