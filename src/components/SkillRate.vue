<template>
  <div class="tag">{{ name }}</div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'SkillRate',
  props: {
    name: String,
    rate: Number,
  },
});
</script>

<style scoped lang="less">
@import '../css/variables.less';

.tag {
  display: inline-block;
  border: 1px solid var(--skillborder);
  border-radius: 3px;
  padding: 2px 9px;
  font-size: 0.78rem;
  color: var(--text);
  letter-spacing: 0.02em;
}
</style>
