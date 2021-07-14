<template>
  <div class="container">
    <div class="logo-con">
      <img src="@/assets/images/logo.svg" alt="logo" />
    </div>
    <div class="text-con">
      <h3>Log in to your account</h3>
    </div>
    <div class="content">
      <form class="form">
        <div class="input-div">
          <label class="new-input"> Email Address</label> <br />
          <input v-model="email" type="text" class="" />
        </div>

        <div class="input-div">
          <label class="confirm"> Password</label> <br />
          <input id="password" v-model="password" :type="type" />
          <p class="hide-img" @click="showPassword()">{{ showHidepass }}</p>
        </div>
        <div class="forgot-password">
          <h3>
            <nuxt-link to="/forgot-password" class="link"
              >Forgot password?</nuxt-link
            >
          </h3>
        </div>
        <div class="btn">
          <button class="save-btn" @click="login()">
            <Loader v-show="loading" />
            <span v-show="!loading">Log in</span>
          </button>
        </div>
      </form>
      <div class="new-user">
        <p>
          Don't have an account?
          <span><nuxt-link to="/signup" class="link">Sign up</nuxt-link> </span>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import Cookies from 'js-cookie'

export default {
  data() {
    return {
      type: 'password',
      email: '',
      password: '',
      showHidepass: 'Show',
      loading: false,
    }
  },
  methods: {
    showPassword() {
      if (this.type === 'password') {
        this.type = 'text'
        this.showHidepass = 'Hide'
      } else if (this.type === 'text') {
        this.type = 'password'
        this.showHidepass = 'Show'
      }
    },
    login() {
      this.loading = true
      this.errMsg = ''
      fetch(this.$store.state.baseurl + '/user/auth/signin', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          email: this.email,
          password: this.password,
        }),
      })
        .then((resp) => resp.json())
        .then((data) => {
          this.loading = false

          if (!data.error) {
            console.log(data.data)
            Cookies.set('email', `${data.data.email}`)
            Cookies.set('password', `${data.data.password}`)
            // this.$store.commit('setToken', data.data.token)
            // this.$store.commit('setAdminDetails', data.data.profile)
            this.$router.push('/')
          } else {
            this.errMsg = data.msg
          }
        })
        .catch((err) => this.$toasted.error(err, { duration: 3600 }))
    },
  },
}
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
  .container .text-con {
    margin-top: 73.75px;
    margin-bottom: 33px;
  }
  .text-con {
    display: flex;
    justify-content: center;
  }
  .text-con h3 {
    font-size: 18px;
    line-height: 21px;
  }
  .forgot-password {
    display: flex;
    justify-content: flex-end;
    margin-right: 20px;
  }
  .forgot-password a {
    color: #990c0c;
    font-size: 14px;
    line-height: 17px;
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
    cursor: pointer;
    top: 60px;
    right: 40px;
    color: rgba(0, 0, 0, 0.726);
    font-size: 14px;
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

  .save-btn span {
    color: white;
  }
  .content {
    width: 90%;
    margin: 10px auto;
  }
  .new-user p {
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
