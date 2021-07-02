<template>
  <swiper ref="mySwiper" :options="swiperOptions">
    <swiper-slide>
      <div class="bg-area">
        <p class="skip">Skip >></p>
        <img src="@/assets/feelings.svg" alt="" />
        <h1>Save Lives</h1>
        <p class="text">
          With Danger Notify you are in the position to save lives during
          emergency situation
        </p>
        <div class="circles">
          <div class="circle unfill"></div>
          <div class="circle"></div>
          <div class="circle"></div>
          <div class="circle"></div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="bg-area">
        <p class="skip">Skip >></p>
        <img src="@/assets/gps- 1.svg" alt="" />
        <h1>Save Lives</h1>
        <p class="text">
          With Danger Notify you are in the position to save lives during
          emergency situation
        </p>
        <div class="circles">
          <div class="circle"></div>
          <div class="circle unfill"></div>
          <div class="circle"></div>
          <div class="circle"></div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="bg-area">
        <p class="skip">Skip >></p>
        <img src="@/assets/warning- 1.svg" alt="" />
        <h1>Save Lives</h1>
        <p class="text">
          With Danger Notify you are in the position to save lives during
          emergency situation
        </p>
        <div class="circles">
          <div class="circle"></div>
          <div class="circle"></div>
          <div class="circle unfill"></div>
          <div class="circle"></div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="bg-area">
        <p class="skip">Skip >></p>
        <img class="ambulance" src="@/assets/images/Group 49.svg" alt="" />
        <h1>Save Lives</h1>
        <p class="text">
          With Danger Notify you are in the position to save lives during
          emergency situation
        </p>
        <NuxtLink to="/welcome">
          <div class="btn-cont">
            <button type="submit" class="btn">Get Started</button>
          </div>
        </NuxtLink>
        <div class="circles">
          <div class="circle"></div>
          <div class="circle"></div>
          <div class="circle"></div>
          <div class="circle unfill"></div>
        </div>
      </div>
    </swiper-slide>
    <div slot="pagination" class="swiper-pagination"></div>
  </swiper>
</template>

<script>
export default {
  name: 'Carrousel',
  data() {
    return {
      swiperOptions: {
        pagination: {
          el: '.swiper-pagination',
        },
        // Some Swiper option/callback...
      },
    }
  },
  computed: {
    swiper() {
      return this.$refs.mySwiper.$swiper
    },
  },
  mounted() {
    console.log('Current Swiper instance object', this.swiper)
    this.swiper.slideTo(0, 1000, false)
  },
}
</script>

<style scoped>
@media screen and (max-width: 767px) {
  .bg-area {
    height: 100vh;
    width: 100%;
    padding: 40px 30px;
  }

  .skip {
    text-align: right;
    /* color: #fff; */
    font-weight: bold;
    font-size: 13px;
    margin-top: 10%;
  }

  .ambulance {
    width: 90%;
    margin-top: 10%;
  }

  .bg-area img {
    width: 70%;
    margin: auto;
    margin-top: 30%;
    margin-bottom: 5%;
    display: flex;
    justify-content: center;
    text-align: center;
  }

  .bg-area h1 {
    font-size: 25px;
    font-weight: 600;
    text-align: center;
    margin-bottom: 30px;
  }

  .bg-area .text {
    font-size: 14px;
    text-align: center;
    margin: auto;
    width: 90%;
  }

  .circles {
    margin-top: 10%;
    display: flex;
    justify-content: center;
  }

  .circles .circle {
    width: 10px;
    height: 10px;
    background: rgb(0, 0, 0);
    border-radius: 50%;
    margin: 3px;
    border: 2px solid rgb(0, 0, 0);
  }

  .circles .unfill {
    background: transparent;
  }

  .btn-cont {
    display: flex;
    justify-content: center;
  }

  .btn {
    padding: 16px 60px;
    background: #990c0c;
    border-radius: 10px;
    color: white;
    text-align: center;
    margin-top: 20px;
  }
}
</style>
