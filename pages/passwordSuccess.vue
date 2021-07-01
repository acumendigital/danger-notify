<template>
  <div class="container">
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
      <button class="save-btn">
        <nuxt-link to="/home" class="link">Go Home</nuxt-link>
      </button>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
@media screen and (max-width: 767px) {
  .container {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .container .logo-con {
    margin-top: 78px;
  }
  .container .success-con {
    margin-top: 72.75px;
  }
  .container .text-con {
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
  .save-btn .link {
    background: #990c0c;
    border-radius: 10px;
    font-size: 16px;
    line-height: 19px;
    padding: 17px 129px;
    color: #ffffff;
    text-align: center;
  }
}
@media screen and (min-width: 768px) {
  .container {
    display: none;
  }
}
</style>
