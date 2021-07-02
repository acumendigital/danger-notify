<template>
  <div class="container">
    <div class="logo-con">
      <img src="@/assets/images/logo.svg" alt="logo" />
    </div>
    <div class="content">
      <form class="form">
        <div class="input-div">
          <label class="new-input"> First Name</label> <br />
          <input type="text" class="" />
        </div>
        <div class="input-div">
          <label class="new-input"> Last Name</label> <br />
          <input type="text" class="" />
        </div>
        <div class="input-div">
          <label class="new-input"> Email Address</label> <br />
          <input type="text" class="" />
        </div>
        <div class="input-div">
          <label class="new-input"> Phone Number</label> <br />
          <input type="text" class="" />
        </div>

        <div class="input-div">
          <label class="confirm"> Password</label> <br />
          <input type="text" class="" />
          <img src="@/assets/images/hide.svg" alt="logo" class="hide-img" />
        </div>
        <div class="btn">
          <button class="save-btn">Sign up</button>
        </div>
      </form>
      <div class="old-user">
        <p>
          Already have an account?
          <span>
            <nuxt-link to="/login" class="link">Log In</nuxt-link>
          </span>
        </p>
      </div>
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
  .container .text-con {
    margin-top: 73.75px;
    margin-bottom: 33px;
  }

  .form {
    width: 100%;
    text-align: left;
  }
  .form .new-input,
  .form .confirm {
    font-size: 16px;
    line-height: 19px;
    padding-top: 30px;
    padding-left: 20px;
    margin-top: 20px;
  }
  .form input {
    border: 1px solid rgba(0, 0, 0, 0.15);
    box-sizing: border-box;
    border-radius: 10px;
    width: 300px;
    margin-top: 20px;
    margin-left: 20px;
    padding: 15px;
    margin-bottom: 20px;
  }
  .input-div {
    position: relative;
    width: 100%;
  }
  .hide-img {
    position: absolute;
    top: 50px;
    right: 50px;
  }

  .btn {
    width: 100%;

    margin: 55px auto;
  }
  .btn .save-btn {
    width: 300px;
    background: #990c0c;
    border-radius: 10px;
    font-size: 16px;
    line-height: 19px;
    padding: 17px 159px;
    color: #ffffff;
    cursor: pointer;
    width: 300px;
    margin-top: 20px;
    margin-left: 20px;
    padding: 15px;
    margin-bottom: 20px;
  }
  .content {
    width: 90%;
    margin: 10px auto;
  }
  .old-user p {
    padding-left: 20px;
    text-align: center;
  }
  span .link {
    color: #990c0c;
  }
}
@media screen and (min-width: 768px) {
  .container {
    display: none;
  }
}
</style>
