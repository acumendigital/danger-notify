<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div class="content">
        <h6>Candidates Details</h6>
        <div class="tabs">
          <div
            :class="activeTab.includes('basic-details') ? 'active' : 'inactive'"
            class="basic-details"
            @click="activeTab = 'basic-details'"
          >
            Basic Details
          </div>
          <div
            :class="activeTab.includes('reports') ? 'active' : 'inactive'"
            class="reports"
            @click="activeTab = 'reports'"
          >
            Reports
          </div>
        </div>
        <div v-show="activeTab == 'basic-details'" class="tab-1 basic-details">
          <div class="details-container">
            <p class="title">User ID:</p>
            <p class="detail">HE55778</p>
          </div>
          <div class="details-container">
            <p class="title">Fullname:</p>
            <p class="detail">Precious Makinde</p>
          </div>
          <div class="details-container">
            <p class="title">Phone Number:</p>
            <p class="detail">+44 829 9015 2482</p>
          </div>
          <div class="details-container">
            <p class="title">Age:</p>
            <p class="detail">28</p>
          </div>
          <div class="details-container">
            <p class="title">Email:</p>
            <p class="detail">precious@makindeorg.com</p>
          </div>
          <div class="details-container">
            <p class="title">Origin State:</p>
            <p class="detail">Kaduna</p>
          </div>
          <div class="details-container">
            <p class="title">Residence:</p>
            <p class="detail">Lagos</p>
          </div>
          <div class="details-container">
            <p class="title">Availabilty:</p>
            <p class="detail">Live Out</p>
          </div>
          <div class="details-container">
            <p class="title">Rating:</p>
            <p class="detail">3.5</p>
          </div>
          <div class="details-container">
            <p class="title">Unique Skill(s):</p>
            <p class="detail">
              Fluent in 5 Languages - English, Yoruba, Hausa, Igbo and Igala.
            </p>
          </div>
          <div class="details-container">
            <p class="title">Experience:</p>
            <p class="detail">2 Years +</p>
          </div>
          <div class="details-container">
            <p class="title">Gender:</p>
            <p class="detail">Female</p>
          </div>
          <div class="details-container">
            <p class="title">Work History:</p>
            <p class="detail">Live Out</p>
          </div>
        </div>
        <div v-show="activeTab == 'reports'" class="tab-2">
          <div class="reports-title">
            <p>Reports Available:</p>
          </div>
          <div class="reports-available">
            <div>
              <img src="~assets/images/tick.svg" alt="tick" /><span
                class="sub-text"
                >Identity Verification</span
              ><span class="view-report">View Report</span>
            </div>
            <div>
              <img src="~assets/images/tick.svg" alt="tick" /><span
                class="sub-text"
                >Criminal Record</span
              ><span class="view-report">View Report</span>
            </div>
            <div>
              <img src="~assets/images/tick.svg" alt="tick" /><span
                class="sub-text"
                >Medical Profile and History</span
              ><span class="view-report">View Report</span>
            </div>
            <div>
              <img src="~assets/images/tick.svg" alt="tick" /><span
                class="sub-text"
                >Residencial Address Verification</span
              ><span class="view-report">View Report</span>
            </div>
            <div>
              <img src="~assets/images/tick.svg" alt="tick" /><span
                class="sub-text"
                >Guarantors Profile Verification</span
              ><span class="view-report">View Report</span>
            </div>
            <div>
              <img src="~assets/images/tick.svg" alt="tick" /><span
                class="sub-text"
                >Work History Verification</span
              ><span class="view-report">View Report</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="close" @click="$emit('close-candidateDetails')">
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
  overflow-y: auto;
}

.modal {
  margin-top: 10%;
  background-color: white;
  width: 698px;
  border-radius: 8px;
}

.close {
  margin-top: 10%;
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

.reports {
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
