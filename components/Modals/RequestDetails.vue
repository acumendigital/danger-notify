<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div class="content">
        <h6>Requests Details</h6>
        <div class="tabs">
          <div
            :class="activeTab.includes('basic-details') ? 'active' : 'inactive'"
            class="basic-details"
            @click="activeTab = 'basic-details'"
          >
            Basic Details
          </div>
          <div
            :class="activeTab.includes('full-details') ? 'active' : 'inactive'"
            class="full-details"
            @click="activeTab = 'full-details'"
          >
            Full Details
          </div>
        </div>
        <div v-show="activeTab == 'basic-details'" class="tab-1 basic-details">
          <div class="details-container">
            <p class="title">Fullname:</p>
            <p class="detail">Precious Makinde</p>
          </div>
          <div class="details-container">
            <p class="title">Email:</p>
            <p class="detail">precious@makindeorg.com</p>
          </div>
          <div class="details-container">
            <p class="title">Phone Number:</p>
            <p class="detail">+44 829 9015 2482</p>
          </div>
          <div class="details-container">
            <p class="title">Pending Requests:</p>
            <p class="detail">56</p>
          </div>
          <div class="details-container">
            <p class="title">Active Requests:</p>
            <p class="detail">82</p>
          </div>
          <div class="details-container">
            <p class="title">Completed Requests:</p>
            <p class="detail">94</p>
          </div>
        </div>
        <div v-show="activeTab == 'full-details'" class="tab-2">
          <RequestFullDetails />
        </div>
      </div>
    </div>
    <div class="close" @click="$emit('close-requestDetails')">
      <img src="@/assets/images/close.svg" alt="close" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeTab: 'basic-details',
    }
  },
}
</script>

<style scoped>
.modal-backdrop {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(24, 18, 46, 0.8);
  display: flex;
  justify-content: center;
  align-items: flex-start;
}

.modal {
  margin-top: 6%;
  background-color: white;
  width: 698px;
  border-radius: 8px;
  height: 650px;
  overflow-y: auto;
}

.close {
  margin-top: 6%;
  margin-left: 16px;
  cursor: pointer;
}

.content {
  width: 75%;
  margin: 80px 80px;
}

.content h6 {
  font-size: 25px;
  font-weight: 500;
  color: black;
  margin-bottom: 42px;
}

.basic-details {
  border-radius: 8px 0 0 8px;
}

.full-details {
  border-radius: 0 8px 8px 0;
}

.tabs {
  background-color: #f9fafb;
  display: flex;
  width: 500px;
  border-radius: 8px;
  margin-bottom: 60px;
}

.tabs div {
  padding: 20px 60px;
  width: 250px;
  text-align: center;
  border: none;
  background-color: transparent;
  cursor: pointer;
}

.tabs div:hover {
  background-color: #00a69d;
  color: white;
}

.active {
  background-color: #00a69d !important;
  color: white;
}

/* BASIC DETAILS  */

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

/* REPORTS  */

.tab-2 {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}

.reports-available > div {
  margin-bottom: 20px;
}

.sub-text {
  font-size: 15px;
  padding-left: 8px;
}

.view-report {
  font-size: 14px;
  padding-left: 12px;
  color: #384bf9;
  cursor: pointer;
}
</style>
