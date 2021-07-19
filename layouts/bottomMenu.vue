<template>
  <div class="app">
    <div class="main-section">
      <Nuxt />
    </div>
    <div class="bottom-nav">
      <BottomNav />
    </div>
  </div>
</template>

<script>
import bottomNav from '~/components/BottomNav.vue'
export default {
  components: { bottomNav },
}
</script>

<style>
html {
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
/* .bottom-nav {
  position: fixed;
  width: 100%;
} */
.main-section {
  overflow: auto;
}
@media only screen and (min-width: 767px) {
  html {
    display: none;
  }
}

.app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
</style>
