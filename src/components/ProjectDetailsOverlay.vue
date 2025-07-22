<template>
  <transition name="fade">
    <div v-if="visible">
      <div class="overlay" @click="$emit('close')"></div>
      <div class="dialog" :style="{ 'background-color': 'var(--card-bg)', 'color': 'var(--text-color)' }">
        <button @click="$emit('close')" class="dialog-close" aria-label="Close">
          <span>✕</span>
        </button>
        <h1 class="dialog-title">{{ title }}</h1>
        <div class="dialog-content">
          <div v-html="htmlContent"></div>
        </div>
      </div>
    </div>
  </transition>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "ProjectDetailsOverlay",
  props: {
    visible: Boolean,
    color: String,
    title: String,
    htmlContent: String,
  },
  methods: {
    getImage: function(url: string) {
      console.log("fetching image " + url);
    }
  }
});
</script>

<style scoped>
.overlay {
  background-color: rgba(0,0,0,0.45);
  z-index: 10;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  transition: background 0.3s;
}

.dialog {
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  margin: 40px auto;
  z-index: 11;
  max-width: 1000px;
  min-width: 320px;
  width: 95vw;
  background: var(--card-bg);
  color: var(--text-color);
  border-radius: 16px;
  box-shadow: 0 8px 40px rgba(0,0,0,0.18);
  padding: 24px 16px 16px 16px;
  max-height: 90vh;
  overflow-y: auto;
  animation: popup-in 0.22s cubic-bezier(.4,2,.6,1) both;
}

@keyframes popup-in {
  0% { opacity: 0; transform: translateY(-24px) scale(0.98); }
  100% { opacity: 1; transform: translateY(0) scale(1); }
}

.dialog-title {
  text-align: center;
  font-size: 1.3em;
  font-weight: 800;
  margin: 0 0 18px 0;
  color: var(--accent-color);
}

.dialog-content {
  font-size: 1.08em;
  line-height: 1.7em;
  color: var(--text-color);
  padding-bottom: 8px;
}

.dialog-close {
  position: absolute;
  top: 14px;
  right: 14px;
  background: var(--accent-color);
  color: var(--card-bg);
  border: none;
  border-radius: 50%;
  width: 32px;
  height: 32px;
  font-size: 1.1em;
  font-weight: 900;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  transition: background 0.2s, color 0.2s;
}
.dialog-close:hover {
  background: var(--text-color);
  color: var(--accent-color);
}

@media (max-width: 700px) {
  .dialog {
    min-width: 0;
    width: 98vw;
    max-width: 98vw;
    max-height: 98vh;
    padding: 12px 2px 12px 2px;
    border-radius: 0.7em;
    margin: 12px auto;
  }
  .dialog-title {
    font-size: 1.08em;
    margin-bottom: 10px;
  }
}
</style>
