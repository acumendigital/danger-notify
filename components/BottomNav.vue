<template>
  <div class="items">
    <nav class="nav-items">
      <div class="nav-item" @click="$router.push('/')">
        <img src="~assets/image/house.png" />
        <div class="nav-title">Home</div>
      </div>
      <div class="nav-item" @click="$router.push('/contacts')">
        <img src="~assets/image/phonecall.png" />
        <div class="nav-title">Contacts</div>
      </div>
      <div class="nav-item" @click="$router.push('/profile')">
        <img src="~assets/image/user.png" />
        <div class="nav-title">User</div>
      </div>
    </nav>
  </div>
</template>
<style scoped>
img {
  width: 20px;
}

.items {
  /* position: fixed; */
  width: 100%;
}

.nav-items {
  display: flex;
  justify-content: space-between;
  padding: 20px 40px 20px 40px;
  border-radius: 30px 30px 0 0;
}
.nav-item {
  text-align: center;
}
</style>
