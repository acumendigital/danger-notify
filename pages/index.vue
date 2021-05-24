<template>
  <div class="dashboard">
    <h6 class="welcome-text">Welcome Back, Oluwaseun</h6>
    <p class="request-text">You have 19 new requests and other tasks to do</p>
    <div class="card-container">
      <div class="card">
        <img src="@/assets/images/total-candidate.svg" alt="img" />
        <div class="card-details">
          <p class="card-number">830</p>
          <p class="card-text">Total Candidates</p>
        </div>
      </div>
      <div class="card">
        <img src="@/assets/images/total-customers.svg" alt="img" />
        <div class="card-details">
          <p class="card-number">280</p>
          <p class="card-text">Total Candidates</p>
        </div>
      </div>
      <div class="card">
        <img src="@/assets/images/total-request.svg" alt="img" />
        <div class="card-details">
          <p class="card-number">200</p>
          <p class="card-text">Total Candidates</p>
        </div>
      </div>
    </div>
    <!-- <div class="tabs">
      <div class="tab-1">Customer</div>
      <div class="tab-2">Candidates</div>
    </div> -->
    <div>
      <DashboardTable />
    </div>
  </div>
</template>

<script>
export default {
  layout: 'Main',
}
</script>

<style scoped>
.dashboard {
  padding: 74px 64px;
}

.welcome-text {
  font-size: 32px;
  font-weight: 600;
  color: black;
  margin-bottom: 30px;
}

.request-text {
  font-size: 15px;
}

/* CARDS  */

.card-container {
  display: flex;
  margin-top: 50px;
}

.card {
  display: flex;
  background-color: white;
  padding: 46px 32px;
  border-radius: 16px;
  align-content: flex-start;
  width: 307px;
  margin-right: 16px;
}

.card-details {
  margin-left: 24px;
}

.card-number {
  font-size: 30px;
  font-weight: 600;
  color: #171717;
}

.card-text {
  color: black;
  margin-top: 10px;
  font-size: 15px;
}

/* TABS  */
/* 
.tabs {
  float: right;
  display: flex;
}

.tab-1 {
  background-color: #00a69d;
} */
</style>
