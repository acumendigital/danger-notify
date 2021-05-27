<template>
  <div class="candidate">
    <div class="content">
      <div class="top-section">
        <h6>Candidates</h6>
        <button class="add-candidate" @click="candidateRegistration = true">
          Add Candidates
        </button>
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
          <p class="table-top-text">All Customers (1028)</p>
        </div>
        <tr class="table-head">
          <th class="user td-th">User ID</th>
          <th class="reg-date td-th">Registration Date</th>
          <th class="full-name td-th">Full Name</th>
          <th class="email td-th">Email Address</th>
          <th class="td-th">Category</th>
        </tr>
        <tr
          v-for="el in tableElements"
          :key="el.userId"
          class="table-body"
          @click="candidateDetails = true"
        >
          <td class="user td-th">{{ el.userId }}</td>
          <td class="reg-date td-th">{{ el.regDate }}</td>
          <td class="full-name td-th">{{ el.fullName }}</td>
          <td class="email td-th">{{ el.email }}</td>
          <td class="category td-th">
            {{ el.category }}
          </td>
        </tr>
      </table>
    </div>
    <CandidateDetails
      v-show="candidateDetails"
      @close-candidateDetails="candidateDetails = false"
    />
    <CandidateRegistration
      v-show="candidateRegistration"
      @close-candidateRegistration="candidateRegistration = false"
    />
  </div>
</template>

<script>
import CandidateDetails from '@/components/Modals/CandidateDetails.vue'
import CandidateRegistration from '@/components/Modals/CandidateRegistration.vue'
export default {
  components: {
    CandidateDetails,
    CandidateRegistration,
  },
  layout: 'Main',
  data() {
    return {
      candidateDetails: false,
      candidateRegistration: false,
      tableElements: [
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          category: 'Chef',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          category: 'Driver',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          category: 'Cleaner',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          category: 'Dry Cleaner',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          category: 'Butler',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          category: 'Chef',
        },
      ],
    }
  },
}
</script>

<style scoped>
.candidate {
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
  cursor: pointer;
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
/* 
.category {
  color: rgba(0, 166, 157, 1);
} */

/* @media only screen and (max-width: 1550px) {
  .search-section {
    flex-basis: 10%;
  }
} */
</style>
