<template>
  <div class="containerSuccess">
    <div class="logo-con">
      <img src="@/assets/images/logo.svg" alt="logo" />
    </div>
    <div class="success-logo">
      <img src="@/assets/images/success.svg" alt="success" :class="iconW" />
    </div>
    <div class="text-con">
      <h3>Success</h3>
      <p>You have Successfully changed your password</p>
    </div>
    <div class="btn">
      <button class="save-btn">Go Home</button>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
.containerSuccess {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.containerSuccess .logo-con {
  margin-top: 78px;
}
.containerSuccess .success-con {
  margin-top: 72.75px;
}
.containerSuccess .text-con {
  margin-top: 42.8px;
  margin-bottom: 50px;
}
.text-con h3 {
  font-size: 36px;
  line-height: 43px;
  text-align: center;
}
.text-con p {
  font-size: 16px;
  line-height: 19px;
  text-align: center;
  padding-top: 23px;
}
.btn {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 55px 20px;
  width: 359px;
}
.btn .save-btn {
  background: #990c0c;
  border-radius: 10px;
  font-size: 16px;
  line-height: 19px;
  padding: 17px 159px;
  color: #ffffff;
  text-align: center;
}
</style>
