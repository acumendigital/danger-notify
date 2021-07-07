<template>
  <div>
    <div class="contacts">
      <button class="saved">
        <img
          class="left-arrow"
          src="~assets/image/vector.png"
          @click="$router.go(-1)"
        />
        Add New Contact
        <h3 class="save">Save</h3>
      </button>
    </div>
    <div class="image">
      <img class="user" src="~assets/image/group 41.png" />
    </div>
    <div class="container">
      <form class="form">
        <div class="form-group">
          <label>Name</label>
          <input v-model="name" type="text" />
        </div>
        <div class="form-group">
          <label>Relationship</label>
          <input v-model="relationship" type="text" />
        </div>
        <div class="form-group">
          <label>Phone Number</label>
          <input v-model="phone" type="tel" />
        </div>
        <div class="form-group">
          <label>Email Address</label>
          <input v-model="email" type="email" />
        </div>
      </form>
    </div>
    <div class="btn" role="button">
      <button class="save-btn" @click="saveContact()">
        <Loader v-show="loading" />
        <span v-show="!loading">Save</span>
      </button>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      loading: false,
      name: '',
      relationship: '',
      phone: '',
      email: '',
    }
  },
  methods: {
    saveContact() {
      this.loading = true
      this.errMsg = ''
      fetch(this.$store.state.baseUrl + '/user/contact/add_contact', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
          Accept: 'application/json',
        },
        body: JSON.stringify({
          name: this.name,
          relationship: this.relationship,
          email: this.email,
          phone: this.phone,
        }),
      })
        .then((response) => response.json())
        .then((data) => {
          this.loading = false
          console.log(data)
          if (!data.error) {
            this.$store.commit('setToken', data.data.token)
            this.$store.commit('setAdminDetails', data.data.profile)
            this.$router.push('/contactSaved')
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
.container {
  padding: 0 15px;
}
.saved {
  background-color: white;
  border: none;
  box-shadow: 0 4px 8px 0 rgba(107, 107, 107, 0.2),
    0 6px 20px 0 rgba(131, 130, 130, 0.19);
  width: 345px;
  height: 60px;
  border-radius: 12px;
  margin: auto;
  margin-top: 30px;
  color: black;
  font-weight: 600;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0px 10px;
}
.contacts {
  text-align: center;
}
.save {
  color: #990c0c;
}
.left-arrow {
  width: 10px;
}
.user {
  border-radius: 50%;
  width: 90px;
  margin-top: 25px;
}
.image {
  text-align: center;
}
.form-group {
  width: 100%;
  margin-top: 15px;
  display: flex;
  flex-direction: column;
}

.form-group label {
  font-size: 16px;
  color: #000;
  margin-bottom: 5px;
}

.form-group input {
  width: 100%;
  height: 45px;
  border: 1px solid rgba(0, 0, 0, 0.15);
  box-sizing: border-box;
  border-radius: 10px;
  padding-left: 15px;
  color: rgba(0, 0, 0, 0.5);
}
/* .btn {
  width: 350px;
  height: 54px;
  margin: 0 auto;
  background: #990c0c;
  border-radius: 10px;
  margin-top: 60px;
} */

.btn {
  width: 350px;
  margin: 0 auto;
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
.saving {
  color: #fff;
  text-align: center;
  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  padding: 15px;
}
</style>
