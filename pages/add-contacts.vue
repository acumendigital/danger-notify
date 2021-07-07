<template>
  <div class="container">
    <div class="logo-con">
      <img src="@/assets/images/logo.svg" alt="icon" :class="iconW" />
    </div>
    <div class="text-con">
      <h3>Add Emergency Contact</h3>
      <p>Add two Emergency Contacts before you continue</p>
    </div>
    <div class="add" @click="$router.push('/newContact')">
      <h5>+ <span class="add-contact">Add Contact</span></h5>
    </div>
    <div class="btn">
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
      errMsg: '',
      name: '',
      relationship: '',
      email: '',
      phone: '',
    }
  },
}
</script>

<style scoped>
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
  .container .text-con {
    margin-top: 53.75px;
    font-size: 24px;
    line-height: 28px;
  }
  .text-con h3 {
    text-align: center;
  }
  .text-con p {
    padding-top: 15px;
    font-weight: normal;
    font-size: 14px;
    line-height: 17px;
    text-align: center;
  }
  .container .add {
    margin-top: 60px;
  }
  .add h5 {
    font-size: 14px;
    line-height: 17px;
    color: #990c0c;
  }
  .add-contact {
    font-size: 14px;
    line-height: 17px;
    color: #990c0c;
    padding-left: 15px;
  }
  .btn {
    display: flex;
    flex-direction: column;
    width: 100%;
    justify-content: center;
    align-items: center;
    margin: 75px auto;
  }
  .btn .save-btn {
    width: 359px;
    background: #939393;
    border-radius: 10px;
    font-size: 16px;
    line-height: 19px;
    padding: 17px 159px;
    color: #ffffff;
  }
}
@media screen and (min-width: 768px) {
  .container {
    display: none;
  }
}
</style>
