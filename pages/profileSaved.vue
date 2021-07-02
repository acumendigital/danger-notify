<template>
  <div>
    <img class="logo" src="~assets/image/logo 1.png" />
    <img class="check" src="~assets/image/group 9.png" />
    <div class="saved">
      <p class="contact">Profile Saved</p>
    </div>
    <div class="btn" role="button" @click="$router.push('/')">
      <h4 class="continue">Continue</h4>
    </div>
  </div>
</template>
<style scoped>
.logo {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 40%;
  margin-top: 70px;
}
.check {
  width: 150px;
  display: block;
  margin-left: auto;
  margin-right: auto;
  margin-top: 110px;
}
.contact {
  color: #000000;
  font-size: 36px;
  font-weight: 600;
  font-style: normal;
  line-height: 43px;
}
.saved {
  text-align: center;
}
.btn {
  width: 350px;
  height: 54px;
  margin: 0 auto;
  background: #990c0c;
  border-radius: 10px;
  margin-top: 140px;
}
.continue {
  color: #fff;
  text-align: center;
  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  padding: 15px;
}
</style>
