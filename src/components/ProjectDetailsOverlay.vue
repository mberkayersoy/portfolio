<template>
  <transition name="overlay-fade">
    <div v-if="visible" class="overlay-root">
      <div class="backdrop" @click="$emit('close')" />
      <div class="dialog">
        <div class="dialog-header">
          <h2 class="dialog-title">{{ title }}</h2>
          <button class="close-btn" @click="$emit('close')" aria-label="Close">✕</button>
        </div>
        <div class="dialog-body">
          <div class="dialog-content" v-html="htmlContent" />
        </div>
      </div>
    </div>
  </transition>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'ProjectDetailsOverlay',
  props: {
    visible: Boolean,
    color: String,
    title: String,
    htmlContent: String,
  },
});
</script>

<style scoped>
/* ── Overlay backdrop ─────────────────────────── */
.backdrop {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.7);
  z-index: 100;
}

/* ── Dialog ───────────────────────────────────── */
.overlay-root {
  position: fixed;
  inset: 0;
  z-index: 100;
  display: flex;
  align-items: flex-start;
  justify-content: center;
  padding: 40px 16px 40px;
  overflow-y: auto;
}

.dialog {
  position: relative;
  z-index: 101;
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 8px;
  width: 100%;
  max-width: 760px;
  animation: slide-in 0.2s ease both;
}

@keyframes slide-in {
  from { opacity: 0; transform: translateY(-16px); }
  to   { opacity: 1; transform: translateY(0); }
}

/* ── Header ───────────────────────────────────── */
.dialog-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px 24px;
  border-bottom: 1px solid var(--border);
}

.dialog-title {
  font-family: 'Syne', sans-serif;
  font-size: 1rem;
  font-weight: 700;
  color: var(--text);
  letter-spacing: 0.02em;
  margin: 0;
  /* override global h2 uppercase */
  text-transform: none;
}

.close-btn {
  background: none;
  border: 1px solid var(--border);
  color: var(--text-muted);
  width: 28px;
  height: 28px;
  border-radius: 4px;
  font-size: 0.75rem;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  transition: color 0.15s, border-color 0.15s;

  &:hover {
    color: var(--text);
    border-color: var(--text);
  }
}

/* ── Body ─────────────────────────────────────── */
.dialog-body {
  padding: 24px;
  font-size: 0.9rem;
  line-height: 1.7;
  color: var(--text);
  max-height: 70vh;
  overflow-y: auto;
}

/* ── Transition ───────────────────────────────── */
.overlay-fade-enter-active,
.overlay-fade-leave-active { transition: opacity 0.18s ease; }
.overlay-fade-enter,
.overlay-fade-leave-to { opacity: 0; }

/* ── Mobile ───────────────────────────────────── */
@media (max-width: 560px) {
  .overlay-root { padding: 0; align-items: flex-end; }
  .dialog {
    border-radius: 12px 12px 0 0;
    max-height: 92vh;
    overflow: hidden;
    display: flex;
    flex-direction: column;
  }
  .dialog-body { flex: 1; max-height: none; }
}
</style>
