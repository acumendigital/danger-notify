<template>
  <div class="container">
    <div class="love">
      <img src="@/assets/feelings.svg" alt="" />
      <h1>Save Lives</h1>
      <p>
        With Danger Notify you are in the position to save lives during
        emergency situation
      </p>
    </div>
    <div class="location">
      <img src="@/assets/gps- 1.svg" alt="" />
      <h1>Save Lives</h1>
      <p>
        With Danger Notify you are in the position to save lives during
        emergency situation
      </p>
    </div>
    <div class="caution">
      <img src="@/assets/warning- 1.svg" alt="" />
      <h1>Save Lives</h1>
      <p>
        With Danger Notify you are in the position to save lives during
        emergency situation
      </p>
    </div>
    <div class="ambulance">
      <img class="van" src="@/assets/ambulance 1.svg" alt="" />
      <img class="asterik" src="@/assets/ambulance-sign 1.svg" alt="" />
      <h1>Save Lives</h1>
      <p>
        With Danger Notify you are in the position to save lives during
        emergency situation
      </p>
      <button>Get Started</button>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
@media screen and (max-width: 767px) {
  div.love,
  div.location,
  div.caution,
  div.ambulance {
    text-align: center;
  }
  div h1 {
    font: Rubik;
    font-weight: 700px;
    font-style: normal;
    font-size: 36px;
    line-height: 20px;
    color: black;
    margin-bottom: 25px;
  }
  div p {
    font: Rubik;
    font-weight: 400px;
    font-style: normal;
    font-size: 14px;
    line-height: 20px;
  }
  div.location {
    margin: 25px auto;
  }
  div.location img {
    display: block;
    margin: auto;
    width: 50%;
  }
  div.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .asterik {
    position: relative;
    bottom: 250px;
    left: 100px;
  }
  .van {
    position: relative;
    top: 100px;
  }
  button {
    position: absolute;
    width: 212px;
    height: 52px;
    left: 90px;
    background: #990c0c;
    border-radius: 10px;
    color: white;
    margin-top: 20px;
  }
}
</style>
