<template>
  <div class="full-details">
    <div class="tabs">
      <div
        :class="activeTab.includes('active-request') ? 'active' : 'inactive'"
        class="active-request"
        @click="activeTab = 'active-request'"
      >
        Active Requests
      </div>
      <div
        :class="activeTab.includes('pending-request') ? 'active' : 'inactive'"
        class="pending-request"
        @click="activeTab = 'pending-request'"
      >
        Pending Requests
      </div>
      <div
        :class="activeTab.includes('completed-request') ? 'active' : 'inactive'"
        class="completed-request"
        @click="activeTab = 'completed-request'"
      >
        Completed Requests
      </div>
    </div>
    <div v-show="activeTab == 'active-request'" class="tab-1 active-request">
      <div class="details-section">
        <div class="details-container">
          <p class="title">Candidates Name:</p>
          <p class="detail">Precious Makinde</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Date:</p>
          <p class="detail">10.10.2019</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Type:</p>
          <p class="detail">Fulltime Engagement</p>
        </div>
        <div class="details-container">
          <p class="title">Category:</p>
          <p class="detail">Chef</p>
        </div>
      </div>
      <div class="details-section">
        <div class="details-container">
          <p class="title">Candidates Name:</p>
          <p class="detail">Precious Makinde</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Date:</p>
          <p class="detail">10.10.2019</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Type:</p>
          <p class="detail">Fulltime Engagement</p>
        </div>
        <div class="details-container">
          <p class="title">Category:</p>
          <p class="detail">Chef</p>
        </div>
      </div>
      <div class="details-section">
        <div class="details-container">
          <p class="title">Candidates Name:</p>
          <p class="detail">Precious Makinde</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Date:</p>
          <p class="detail">10.10.2019</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Type:</p>
          <p class="detail">Fulltime Engagement</p>
        </div>
        <div class="details-container">
          <p class="title">Category:</p>
          <p class="detail">Chef</p>
        </div>
      </div>
    </div>
    <div v-show="activeTab == 'pending-request'" class="tab-2">
      <div class="details-section">
        <div class="details-container">
          <p class="title">Candidates Name:</p>
          <p class="detail">Precious Makinde</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Date:</p>
          <p class="detail">10.10.2019</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Type:</p>
          <p class="detail">Fulltime Engagement</p>
        </div>
        <div class="details-container">
          <p class="title">Category:</p>
          <p class="detail">Chef</p>
        </div>
        <div class="bottom-btn">
          <input id="accept-btn" type="button" value="Accept" />
          <input id="decline-btn" type="button" value="Decline" />
        </div>
      </div>
      <div class="details-section">
        <div class="details-container">
          <p class="title">Candidates Name:</p>
          <p class="detail">Precious Makinde</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Date:</p>
          <p class="detail">10.10.2019</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Type:</p>
          <p class="detail">Fulltime Engagement</p>
        </div>
        <div class="details-container">
          <p class="title">Category:</p>
          <p class="detail">Chef</p>
        </div>
        <div class="botton-btn">
          <input id="accept-btn" type="button" value="Accept" />
          <input id="decline-btn" type="button" value="Decline" />
        </div>
      </div>
      <div class="details-section">
        <div class="details-container">
          <p class="title">Candidates Name:</p>
          <p class="detail">Precious Makinde</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Date:</p>
          <p class="detail">10.10.2019</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Type:</p>
          <p class="detail">Fulltime Engagement</p>
        </div>
        <div class="details-container">
          <p class="title">Category:</p>
          <p class="detail">Chef</p>
        </div>
        <div class="botton-btn">
          <input id="accept-btn" type="button" value="Accept" />
          <input id="decline-btn" type="button" value="Decline" />
        </div>
      </div>
    </div>
    <div v-show="activeTab == 'completed-request'" class="tab-3">
      <div class="details-section">
        <div class="details-container">
          <p class="title">Candidates Name:</p>
          <p class="detail">Precious Makinde</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Date:</p>
          <p class="detail">10.10.2019</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Type:</p>
          <p class="detail">Fulltime Engagement</p>
        </div>
        <div class="details-container">
          <p class="title">Category:</p>
          <p class="detail">Chef</p>
        </div>
        <div class="details-container">
          <p class="title">Subscription Type:</p>
          <p class="detail">Quaterly</p>
        </div>
        <div class="details-container">
          <p class="title">End Date:</p>
          <p class="detail">10.10.2019</p>
        </div>
      </div>
      <div class="details-section">
        <div class="details-container">
          <p class="title">Candidates Name:</p>
          <p class="detail">Precious Makinde</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Date:</p>
          <p class="detail">10.10.2019</p>
        </div>
        <div class="details-container">
          <p class="title">Hire Type:</p>
          <p class="detail">Fulltime Engagement</p>
        </div>
        <div class="details-container">
          <p class="title">Category:</p>
          <p class="detail">Chef</p>
        </div>
        <div class="details-container">
          <p class="title">Subscription Type:</p>
          <p class="detail">Quaterly</p>
        </div>
        <div class="details-container">
          <p class="title">End Date:</p>
          <p class="detail">10.10.2019</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeTab: 'active-request',
    }
  },
}
</script>

<style scoped>
/* TABS  */

.tabs {
  display: flex;
  border-bottom: 1px solid #e4e4e4;
  /* margin-bottom: 50px; */
}

.tabs div {
  padding: 15px 15px;
  cursor: pointer;
}

.active {
  border-bottom: 1px solid #00a69d;
  color: #00a69d;
}

/* FULL DETAILS  */

.details-section {
  padding: 40px 0 20px 0;
  border-bottom: 1px solid #e4e4e4;
}

.details-container {
  display: flex;
  margin-bottom: 30px;
}

.title {
  font-size: 16px;
  color: #767676;
  flex-basis: 35%;
}

.detail {
  font-weight: 600;
  flex-basis: 65%;
}

#bottom-btn {
  display: flex;
  align-items: center;
  margin-bottom: 30px;
}

#accept-btn {
  color: #f7f8fa;
  background-color: #00a69d;
  padding: 13px 50px;
  border-radius: 8px;
  border: none;
  cursor: pointer;
}

#decline-btn {
  color: #717f88;
  border: none;
  background-color: transparent;
  margin-left: 40px;
  cursor: pointer;
}
</style>
