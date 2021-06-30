<template>
  <div class="containerSuccess">
    <div class="logo-con">
      <img src="@/assets/images/logo.svg" alt="logo" />
    </div>

    <div class="text-con">
      <h3>Forgot Password</h3>
    </div>
    <div>
      <p>
        Please, enter your email address. You will receive a link to create a
        new password via email.
      </p>
    </div>
    <form class="form">
      <div>
        <label class="new-input"> Email Address</label> <br />
        <input type="text" class="" />
      </div>
      <div class="btn">
        <button class="save-btn">Send</button>
      </div>
    </form>
    <div></div>
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
.containerSuccess .text-con {
  margin-top: 73.75px;
  margin-bottom: 33px;
}

.text-con h3 {
  font-size: 24px;
  line-height: 28px;
}
.form .new-input {
  font-size: 16px;
  line-height: 19px;
}
.form .new-input,
.form .confirm {
  font-size: 16px;
  line-height: 19px;
}
.form input {
  border: 1px solid rgba(0, 0, 0, 0.15);
  box-sizing: border-box;
  border-radius: 10px;
  width: 112px;
}
.btn {
  display: flex;
  flex-direction: column;
  width: 100%;
  justify-content: center;
  align-items: center;
  margin: 55px auto;
}
.btn .save-btn {
  width: 359px;
  background: #990c0c;
  border-radius: 10px;
  font-size: 16px;
  line-height: 19px;
  padding: 17px 159px;
  color: #ffffff;
}
</style>
