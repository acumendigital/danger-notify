<template>
  <div>
    <div class="header-container">
      <Header />
    </div>
    <div class="container">
      <div>
        <SideMenu />
      </div>
      <div class="main-section">
        <Nuxt />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Main',
}
</script>

<style>
html {
  word-spacing: 1px;
  line-height: 18px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  background-color: #f3f6f8;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
/* 
.header-container {

} */

.container {
  display: flex;
  padding-top: 90px;
}

.main-section {
  margin: 20px 0 0 245px;
}
</style>
