<template>
  <div class="container">
    <div class="logo-con">
      <img src="@/assets/images/logo.svg" alt="logo" />
    </div>
    <div class="content">
      <div class="text-con">
        <h3>Forgot Password</h3>
        <p>
          Please, enter your email address. You will receive a link to create a
          new password via email.
        </p>
      </div>
      <form class="form">
        <div class="input-div">
          <label class="new-input"> Email Address</label> <br />
          <input type="text" class="" />
        </div>

        <div class="btn">
          <button class="save-btn">Send</button>
        </div>
      </form>
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

  .text-con h3 {
    font-size: 24px;
    line-height: 28px;
    text-align: left;
    padding-left: 20px;
  }
  .text-con p {
    font-size: 14px;
    line-height: 17px;
    font-weight: normal;
    padding-left: 20px;
    padding-top: 25px;
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
}
@media screen and (min-width: 768px) {
  .container {
    display: none;
  }
}
</style>
