<template>
  <div class="payment">
    <div class="content">
      <div class="top-section">
        <h6>Payments</h6>
        <button class="add-candidate">Add Candidates</button>
      </div>
      <div class="top-input-div">
        <div class="form search-box">
          <label for="search-btn">What are you looking for ?</label>
          <input
            id="search-btn"
            type="search"
            name="search-btn"
            placeholder="Search.."
          />
          <img src="~/assets/images/search.svg" class="search-icon" alt="" />
        </div>
        <div class="form">
          <label for="dates">Registration Date</label>
          <div class="from-div">
            <input
              id="from-date"
              ref="fromdate"
              type="text"
              class="from"
              name="from-date"
              placeholder="From Date"
              @blur="showDateIcon1"
              @focus="hideDateIcon1"
            />
            <img
              v-if="!hideIcon1"
              src="~/assets/images/calendarIcon.svg"
              class="calendar-from"
              alt=""
            />
          </div>
          <div class="to-div">
            <input
              id="to-date"
              ref="todate"
              type="text"
              name="to-date"
              placeholder="To Date"
              @blur="showDateIcon2"
              @focus="hideDateIcon2"
            />
            <img
              v-if="!hideIcon2"
              src="~/assets/images/calendarIcon.svg"
              class="calendar-to"
              alt=""
            />
          </div>
        </div>
        <div class="green-btn" role="button" @click="showDetail = true">
          Refine Search
        </div>
      </div>
      <table>
        <div class="table-top">
          <p class="table-top-text">All Payments (1028)</p>
        </div>
        <tr class="table-head">
          <th class="user td-th">User ID</th>
          <th class="full-name td-th">Full Name</th>
          <th class="email td-th">Email Address</th>
          <th class="category td-th">Category</th>
          <th class="pay-package td-th">Payment Package</th>
          <th class="pay-date td-th">Payment Date</th>
        </tr>
        <tr
          v-for="el in tableElements"
          :key="el.userId"
          class="table-body"
          @click="paymentDetails = true"
        >
          <td class="user td-th">{{ el.userId }}</td>
          <td class="full-name td-th">{{ el.fullName }}</td>
          <td class="email td-th">{{ el.email }}</td>
          <td class="category td-th">
            {{ el.category }}
          </td>
          <td class="pay-package td-th">{{ el.payPackage }}</td>
          <td class="pay-date td-th">{{ el.payDate }}</td>
        </tr>
      </table>
    </div>
    <PaymentCandidateDetails
      v-show="paymentDetails"
      @close-paymentDetails="paymentDetails = false"
    />
  </div>
</template>

<script>
import PaymentCandidateDetails from '@/components/Modals/PaymentCandidateDetails.vue'
export default {
  components: {
    PaymentCandidateDetails,
  },
  layout: 'Main',
  data() {
    return {
      paymentDetails: false,
      tableElements: [
        {
          userId: 'ND1283',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          category: 'Chef',
          payPackage: 'Annual',
          payDate: '23.04.2020',
        },
        {
          userId: 'ND1283',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          category: 'Driver',
          payPackage: 'Quaterly',
          payDate: '23.04.2020',
        },
        {
          userId: 'ND1283',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          category: 'Cleaner',
          payPackage: 'Quaterly',
          payDate: '23.04.2020',
        },
        {
          userId: 'ND1283',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          category: 'Dry Cleaner',
          payPackage: 'Annual',
          payDate: '23.04.2020',
        },
        {
          userId: 'ND1283',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          category: 'Baby Sitter',
          payPackage: 'Annual',
          payDate: '23.04.2020',
        },
        {
          userId: 'ND1283',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          category: 'Driver',
          payPackage: 'Quaterly',
          payDate: '23.04.2020',
        },
      ],
    }
  },
}
</script>

<style scoped>
.payment {
  padding: 70px 41px;
  width: 70vw;
}

.top-section {
  display: flex;
  justify-content: space-between;
  margin-bottom: 32px;
  align-items: center;
  padding-right: 43px;
}

.top-section h6 {
  font-size: 24px;
  font-weight: 500;
  color: black;
}

.add-candidate,
.refine-search {
  color: white;
  background-color: #00a69d;
  padding: 16px 34px;
  border: none;
  border-radius: 8px;
  font-size: 13px;
  font-weight: 500;
  cursor: pointer;
}

#search-btn {
  background: #f9fafb;
  border: 1px solid #e1edfe;
  box-sizing: border-box;
  border-radius: 8px;
  width: 20vw;
  height: 50px;
  margin-right: 1vw;
  position: relative;
  padding-left: 3vw;
}
#from-date,
#to-date {
  background: #ffffff;
  opacity: 0.5;
  border: 1px solid #d1d1d1;
  box-sizing: border-box;
  border-radius: 8px;
  width: 10vw;
  height: 50px;
  margin-right: 24px;
  padding-left: 0.7vw;
  padding-right: 0.38vw;
}
.from-div,
.to-div {
  display: inline;
  position: relative;
}
/* input[type='date']::-webkit-inner-spin-button,
input[type='date']::-webkit-calendar-picker-indicator {
  display: none;
  -webkit-appearance: none;
} */
.calendar-from {
  position: absolute;
  right: 3vw;
  top: 0.2vh;
}
.calendar-to {
  position: absolute;
  right: 2.65vw;
  bottom: 0.3vh;
}
.search-icon {
  position: absolute;
  left: 0.7vw;
  top: 56.4%;
}
.top-input-div {
  left: 286px;
  top: 259px;
  background: #ffffff;
  border-radius: 8px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 25px 43px;
  margin-top: 35px;
}
.search-box {
  position: relative;
}
label {
  display: block;
  padding-bottom: 12px;
  font-size: 15px;
  color: black;
}
.green-btn {
  width: 10vw;
  height: 50px;
  max-height: 7.45vh;
  background: #00a69d;
  border-radius: 8px;
  display: flex;
  margin-top: 3%;
  color: #ffffff;
  font-family: Graphik;
  font-style: normal;
  font-weight: 500;
  font-size: 13px;
  line-height: 14px;
  cursor: pointer;
  justify-content: center;
  align-items: center;
}

/* TABLE  */

table {
  margin-top: 50px;
  width: 100%;
  background-color: white;
  border-radius: 8px;
}

.table-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 25px 40px;
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
  width: 12%;
}

.email {
  width: 28%;
}

.category {
  width: 18%;
}

.pay-package {
  width: 25%;
}
</style>
