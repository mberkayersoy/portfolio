<template>
  <footer class="footer">
    <div class="footer-inner">
      <span>mberkayersoy@gmail.com</span>
      <div class="footer-links">
        <a href="https://github.com/mberkayersoy" target="_blank" rel="noopener">GitHub</a>
        <a href="https://www.linkedin.com/in/berkay-ersoy-291869228/" target="_blank" rel="noopener">LinkedIn</a>
      </div>
    </div>
  </footer>
</template>

<script lang="ts">
import Vue from 'vue';
export default Vue.extend({ name: 'Footer' });
</script>

<style scoped lang="less">
@import '../css/variables.less';

.footer {
  border-top: 1px solid var(--border);
}

.footer-inner {
  max-width: 860px;
  margin: 0 auto;
  padding: 20px 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 0.78rem;
  color: var(--text-muted);
  gap: 16px;
}

.footer-links {
  display: flex;
  gap: 16px;

  a {
    color: var(--text-muted);
    text-decoration: none;
    transition: color 0.15s;
    &:hover { color: var(--text); }
  }
}
</style>
