<template>
  <div class="container">
    <div class="logo-con">
      <img src="@/assets/images/logo.svg" alt="logo" />
    </div>
    <div class="content">
      <div class="features">
        <img src="@/assets/images/FirstAid.svg" alt="FirstAid" />
        <p>One click emergency call</p>
      </div>
      <div class="features">
        <img src="@/assets/images/FirstAid.svg" alt="FirstAid" />
        <p>Add necessary contacts for emergency notification</p>
      </div>
      <div class="features">
        <img src="@/assets/images/FirstAid.svg" alt="FirstAid" />
        <p>Automatic geolocation detection</p>
      </div>
      <div class="features">
        <img src="@/assets/images/FirstAid.svg" alt="FirstAid" />
        <p>Sos Buttons for calling police, fire department, gas department.</p>
      </div>
      <div class="features">
        <img src="@/assets/images/FirstAid.svg" alt="FirstAid" />
        <p>Automatic geolocation detection</p>
      </div>
      <div class="features">
        <img src="@/assets/images/FirstAid.svg" alt="FirstAid" />
        <p>Sos Buttons for calling police, fire department, gas department.</p>
      </div>
      <div class="btn">
        <button class="sign-btn">
          <nuxt-link to="/signUp" class="link">Sign up</nuxt-link>
        </button>
      </div>
      <div class="btn">
        <button class="login-btn">
          <nuxt-link to="/login" class="link">Login</nuxt-link>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
@media screen and (max-width: 767px) {
  .container {
    width: 100%;
    margin: 20px auto;
  }
  .container .logo-con {
    margin: 78px auto;
  }
  .logo-con img {
    display: block;
    margin-left: auto;
    margin-right: auto;
    width: 50%;
  }
  .features {
    display: flex;
    margin-bottom: 15px;
  }
  .features p {
    padding-left: 15px;
  }
  .btn {
    width: 100%;
    display: flex;
  }
  .btn .sign-btn {
    background: #990c0c;
    border-radius: 10px;
    padding: 17px 77px;
    cursor: pointer;
    width: 212px;
    margin: 70px auto 25px auto;
    justify-content: center;
    align-self: center;
    padding: 15px;
  }
  .btn .sign-btn .link {
    color: #fff;
    font-size: 16px;
    line-height: 19px;
  }
  .btn .login-btn {
    background: #fff;
    border-radius: 10px;
    font-size: 16px;
    line-height: 19px;
    padding: 17px 77px;
    border: 3px solid #990c0c;
    color: #000;
    cursor: pointer;
    width: 212px;
    margin: 0px auto;
    justify-content: center;
    align-self: center;
    padding: 15px;
  }
  .content {
    width: 90%;
    margin: 10px auto;
  }
}
@media screen and (min-width: 768px) {
  .container {
    display: none;
  }
}
</style>
