<template>
  <div class="http-404-container">
    <div class="http-404">404 🙈</div>
  </div>
</template>

<style scoped>
.http-404-container {
  width: 100%;
  min-height: 60vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 24px;
  box-sizing: border-box;
}
@media (min-width: 900px) {
  .http-404-container {
    padding: 48px 32px;
  }
}
.http-404 {
  font-size: 11em;
  line-height: 3em;
  text-align: center;
}
</style>
