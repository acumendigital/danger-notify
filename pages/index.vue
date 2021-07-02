<template>
  <div>
    <img class="logo" src="~assets/image/logo 1.png" />
    <img class="menu" src="~assets/image/menu_24px.png" />
    <p class="click">Click button below during emergencies</p>
    <div class="image">
      <img class="group" src="~assets/image/Group 32-2.png" />
    </div>
    <div class="btn">
      <button class="first">
        <img class="aid" src="~assets/image/FirstAid.png" />
        <p class="emergency">Contact emergency center for medical aid</p>
      </button>
      <button class="second">
        <img class="aid" src="~assets/image/FirstAid-2.png" />
        <p class="security">Contact Security agency for support</p>
      </button>
    </div>
  </div>
</template>
<script>
export default {
  layout: 'bottomMenu',
}
</script>
<style scoped>
@media screen and (max-width: 767px) {
  .logo {
    width: 100px;
    margin-left: 15px;
    margin-top: 45px;
  }
  .menu {
    width: 20px;
    margin-left: 210px;
    margin-bottom: 10px;
  }
  .click {
    color: black;
    font-family: Rubik;
    font-size: 14px;
    text-align: center;
    margin-top: 70px;
    font-weight: 600;
  }
  .group {
    width: 231px;
  }
  .image {
    text-align: center;
    margin-top: 25px;
  }
  .btn {
    text-align: center;
    margin-top: 60px;
  }
  .first {
    width: 150px;
    height: 200px;
    background: #ffeaea;
    border-radius: 12px;
    border: none;
    box-shadow: 0 4px 8px 0 rgba(107, 107, 107, 0.2),
      0 6px 20px 0 rgba(131, 130, 130, 0.19);
  }
  .second {
    width: 150px;
    height: 200px;
    background: #ffeaea;
    border-radius: 12px;
    box-shadow: 0 4px 8px 0 rgba(107, 107, 107, 0.2),
      0 6px 20px 0 rgba(131, 130, 130, 0.19);
    border: none;
    margin-left: 15px;
  }
  .aid {
    width: 60px;
  }
  .emergency {
    color: black;
    line-height: 20px;
    margin-top: 20px;
    font-family: Rubik;
    font-size: 14px;
    font-weight: 600;
  }
  .security {
    color: black;
    line-height: 20px;
    margin-top: 20px;
    font-family: Rubik;
    font-size: 14px;
    font-weight: 600;
  }
}
</style>
