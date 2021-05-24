<template>
  <div>
    <div class="settings-container">
      <h3 class="update">Update Your Profile</h3>
      <div class="pic-frame">
        <img src="~/assets/images/profilePic.png" alt="" class="profilepic" />
        <div class="icon-div">
          <img src="~/assets/images/plus.svg" alt="plus" class="plusIcon" />
        </div>
      </div>
      <div class="form">
        <form>
          <div class="input-field first_last">
            <div class="firstname">
              <label for="firstname" class="input-label">First Name</label>
              <input v-model="first_name" type="text" class="input-box-first" />
            </div>
            <div class="lastname">
              <label for="lastname" class="input-label">Last Name</label>
              <input v-model="last_name" type="text" class="input-box-first" />
            </div>
          </div>
          <div class="input-field">
            <label for="email" class="input-label">Email Address</label>
            <input v-model="email" type="email" class="input-box" />
          </div>
          <div class="input-field">
            <label for="number" class="input-label">Phone Number</label>
            <input v-model="number" type="text" class="input-box" />
          </div>
          <div class="input-field">
            <label for="password" class="input-label">Password</label>
            <div class="password">
              <input
                v-model="password"
                type="password"
                name="password"
                class="input-box"
              />
              <p class="showPassword">show</p>
            </div>
          </div>
          <div class="input-field">
            <label for="password" class="input-label">Password</label>
            <div class="password">
              <input
                v-model="password"
                type="password"
                name="password"
                class="input-box"
              />
              <p class="showPassword">show</p>
            </div>
          </div>
          <h3 class="auth">Two Factor Authentication</h3>
          <div class="auth-div">
            <div class="auth-icon">
              <img src="~/assets/images/phone.svg" alt="phone" class="phone" />
              <img src="~/assets/images/g.svg" alt="" />
            </div>
            <div class="auth-text">
              <p>SMS Authentication</p>
              <p class="authText">Google Authentication</p>
            </div>
            <div class="auth-btn">
              <div class="btn1">
                <img src="~/assets/images/onBtn.svg" alt="" />
              </div>
              <div class="btjn2">
                <img src="~/assets/images/offBtn.svg" alt="" />
              </div>
            </div>
          </div>
          <div class="btn-div">
            <button class="btn">Save</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'Main',
  data() {
    return {
      first_name: 'Seyi',
      last_name: 'Makinde',
      email: 'SeyiMakinde@gmail.com',
      number: 93739220,
      password: '**********',
    }
  },
}
</script>

<style lang="css" scoped>
.settings-container {
  background: #ffffff;
  border-radius: 8px;
  width: 66vw;
  margin-left: 54%;
  transform: translate(-50%, 0);
  align-items: center;
  /* text-align: center; */
  margin-top: 11vh;
  display: flex;
  justify-content: center;
  flex-direction: column;
  padding: 10vh 0 15vh;
}
.pic-frame {
  position: relative;
}
.icon-div {
  position: absolute;
  bottom: 1%;
  left: 64%;
  background: #ffffff;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  box-shadow: 0px 4px 16px #f3f6fa;
  padding: auto;
}
.plusIcon {
  position: absolute;
  bottom: 22%;
  left: 28.5%;
}

/* form styles */

.input-field {
  display: flex;
  flex-basis: 90%;
  flex-direction: column;
  margin: 3vh 0 0;
  font-family: Gelion;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 18px;
  /* identical to box height, or 129% */

  color: #6f8a9c;
}
.input-box-first {
  width: 15.3vw;
  height: 9vh;
  padding-left: 1.2vw;
  background: #ffffff;
  border: 1px solid #c4c4c4;
  box-sizing: border-box;
  border-radius: 8px;
}
.input-box {
  width: 30vw;
  height: 9vh;
  padding-left: 1.2vw;
  background: #ffffff;
  border: 1px solid #c4c4c4;
  box-sizing: border-box;
  border-radius: 8px;
}
.input-label {
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 18px;
  color: #042538;
  padding-bottom: 2vh;
  display: block;
}
.first_last {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.showPassword {
  position: absolute;
  top: 50%;
  transform: translate(0, -50%);
  right: 7.8%;
  cursor: pointer;
  font-family: Gelion;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 18px;
  /* identical to box height, or 129% */

  text-align: right;

  color: #042538;
}
.password {
  position: relative;
}
.btn {
  width: 428px;
  height: 56px;
  background: #00a69d;
  border: 2px solid #00a69d;
  box-sizing: border-box;
  border-radius: 8px;
  margin: 8vh 0 1.5vh;
  color: #ffffff;
  font-family: 'Gelion';
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
  line-height: 19px;
  text-align: center;
  cursor: pointer;
}
.auth-div {
  display: flex;
  flex-direction: row;
  margin: 8vh 0 8vh 0;
}
.auth-icon {
  display: flex;
  flex-direction: column;
}
.auth-btn {
  display: flex;
  flex-direction: column;
  cursor: pointer;
}
.auth-text {
  margin: 0 7vw 0 3vw;
  padding-top: 2vh;
  font-family: Gelion;
  font-style: normal;
  font-weight: 600;
  font-size: 18px;
  line-height: 22px;
  color: #c4c4c4;
}
.phone {
  margin-bottom: 3vh;
}
.authText {
  padding-top: 5.5vh;
}
.btn1 {
  margin-bottom: 4vh;
  margin-top: 1.8vh;
}
.auth {
  margin-top: 5vh;
  font-family: Gelion;
  font-style: normal;
  font-weight: 600;
  font-size: 18px;
  line-height: 22px;
  /* identical to box height */

  display: flex;
  align-items: flex-end;
  text-align: center;
  color: #c4c4c4;
}
.update {
  padding-bottom: 6vh;
}
.form {
  margin-top: 3vh;
}
</style>
