<template>
  <div class="container">
    <div class="logo-con">
      <img src="@/assets/images/logo.svg" alt="logo" />
    </div>
    <div class="content">
      <form class="form">
        <div class="input-div">
          <label class="new-input"> First Name</label> <br />
          <input v-model="firstname" type="text" class="" />
        </div>
        <div class="input-div">
          <label class="new-input"> Last Name</label> <br />
          <input v-model="lastname" type="text" class="" />
        </div>
        <div class="input-div">
          <label class="new-input"> Email Address</label> <br />
          <input v-model="email" type="text" class="" />
        </div>
        <div class="input-div">
          <label class="new-input"> Phone Number</label> <br />
          <input v-model="phone" type="text" class="" />
        </div>

        <div class="input-div">
          <label class="confirm"> Password</label> <br />
          <input id="password" v-model="password" :type="type" />
          <p class="hide-img" @click="showPassword()">{{ showHidepass }}</p>
        </div>
        <div class="btn">
          <button class="save-btn" @click="signup()">
            <Loader v-show="loading" />
            <span v-show="!loading">Sign up</span>
          </button>
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
import Cookies from 'js-cookie'

export default {
  data() {
    return {
      firstname: '',
      lastname: '',
      email: '',
      phone: '',
      password: '',
      showHidepass: 'Show',
      loading: false,
      type: 'password',
    }
  },
  created() {
    console.log(Cookies.get('token'))
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
    async signup() {
      this.loading = true
      this.errMsg = ''
      const signupPromise = await fetch(
        this.$store.state.baseurl + '/user/signup',
        {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
          },
          body: JSON.stringify({
            firstname: this.firstname,
            lastname: this.lastname,
            email: this.email,
            phone: this.phone,
            password: this.password,
          }),
        }
      )
      const signupJson = signupPromise.json()
      signupJson
        .then((response) => {
          this.loading = false

          if (!response.error) {
            console.log(response)
            Cookies.set('firstname', `${response.data.firstname}`)
            Cookies.set('lastname', `${response.data.lastname}`)
            Cookies.set('email', `${response.data.email}`)
            Cookies.set('phone', `${response.data.phone}`)
            Cookies.set('password', `${response.data.password}`)
            Cookies.set('token', `${response.token}`)
            // this.$store.commit('setToken', data.data.token)
            // this.$store.commit('setAdminDetails', data.data.profile)
            this.$router.push('/index')
          } else {
            this.$toasted.error(response.message, { duration: 3600 })
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
    margin-top: 10px;
    margin-left: 20px;
    padding: 15px;
    margin-bottom: 30px;
  }
  .input-div {
    position: relative;
    width: 100%;
  }
  .hide-img {
    position: absolute;
    cursor: pointer;
    top: 50px;
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
