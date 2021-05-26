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
    <table>
      <div class="table-top">
        <p class="table-top-text">Resent Sign ups</p>
        <div class="tabs">
          <div
            :class="activeTab.includes('customer-tab') ? 'active' : 'inactive'"
            class="customer-tab"
            @click="activeTab = 'customer-tab'"
          >
            Customer
          </div>
          <div
            :class="
              activeTab.includes('candidates-tab') ? 'active' : 'inactive'
            "
            class="candidates-tab"
            @click="activeTab = 'candidates-tab'"
          >
            Candidates
          </div>
        </div>
      </div>
      <div v-show="activeTab == 'customer-tab'" class="tab-1 customer-tab">
        <tr class="table-head">
          <th class="user td-th">User ID</th>
          <th class="reg-date td-th">Registration Date</th>
          <th class="full-name td-th">Full Name</th>
          <th class="email td-th">Email Address</th>
          <th class="td-th">User Type</th>
        </tr>
        <tr v-for="el in tableElements" :key="el.userId" class="table-body">
          <td class="user td-th">{{ el.userId }}</td>
          <td class="reg-date td-th">{{ el.regDate }}</td>
          <td class="full-name td-th">{{ el.fullName }}</td>
          <td class="email td-th">{{ el.email }}</td>
          <td class="user-type td-th">
            {{ el.userType }}
          </td>
        </tr>
      </div>
      <div v-show="activeTab == 'candidates-tab'" class="tab-2">
        <CandidateTable />
      </div>
    </table>
  </div>
</template>

<script>
export default {
  layout: 'Main',
  data() {
    return {
      activeTab: 'customer-tab',
      tableElements: [
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          userType: 'Customer',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          userType: 'Customer',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          userType: 'Customer',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          userType: 'Customer',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          userType: 'Customer',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          userType: 'Customer',
        },
      ],
    }
  },
}
</script>

<style scoped>
.dashboard {
  padding: 54px 64px;
}

.welcome-text {
  font-size: 28px;
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
  margin-top: 30px;
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

.tabs {
  background-color: #f9fafb;
  display: flex;
  width: 400px;
  border-radius: 8px;
  border: 1px solid #e1edfe;
}

.customer-tab {
  border-radius: 8px 0 0 8px;
}
.candidates-tab {
  border-radius: 0 8px 8px 0;
}

.tabs div {
  padding: 12px 25px;
  font-size: 14px;
  width: 200px;
  text-align: center;
  border: none;
  background-color: transparent;
  cursor: pointer;
}

.tabs div:hover {
  background-color: #00a69d !important;
  color: white;
}

.active {
  background-color: #00a69d !important;
  color: white;
}

/* TABLE  */

table {
  margin-top: 100px;
  width: 100%;
  background-color: white;
  border-radius: 8px;
}

.table-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 18px 40px;
}

.table-top-text {
  font-size: 16px;
  font-weight: 300;
}

.table-head {
  background-color: #f5f8ff;
  padding: 0 40px;
}

tr {
  display: flex;
  padding: 0 40px;
}

th {
  font-weight: 600;
}

.td-th {
  padding: 25px 0;
  width: 20%;
  display: flex;
}

.user {
  width: 15%;
}

.email {
  width: 28%;
}

.user-type {
  color: rgba(247, 148, 29, 1);
}
</style>
