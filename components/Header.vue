<template>
  <div class="header">
    <div class="container-1">
      <img src="@/assets/images/logo.svg" alt="logo" />
      <h1></h1>
    </div>
    <div class="container-2">
      <div class="notification">
        <img src="@/assets/images/notification (1) 1.svg" alt="notification" />
      </div>
      <div class="user">
        <img src="@/assets/images/profile-image.svg" alt="img" />
        <img
          src="@/assets/images/icon/navigation/arrow_drop_down_24px.svg"
          alt="img"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.header {
  position: fixed;
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 30px 45px;
  background-color: white;
  z-index: 2;
  height: 90px;
}

.container-1,
.container-2 {
  display: flex;
  align-items: center;
}

.container-1 h1 {
  margin-left: 73px;
  color: #010025;
  font-weight: 600;
}

.notification {
  margin-right: 32px;
}

.user {
  display: flex;
  align-items: center;
}

.user img {
  margin-left: 12px;
}
</style>
