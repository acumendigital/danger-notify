<template>
  <div>
    <customerDetailModal v-if="showDetail" @close="showDetail = false" />
    <div class="container">
      <h3 class="heading">Customers</h3>
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
      <div class="table-div">
        <p class="table-top-text">All Customers (1028)</p>
        <table>
          <thead>
            <tr class="table-heading">
              <th v-for="(heading, index) in tableHead" :key="index">
                {{ heading }}
              </th>
            </tr>
          </thead>
          <tbody>
            <tr
              v-for="info in tableInfo"
              :key="info.userID"
              class="table-body-row"
            >
              <td>#{{ info.userID }}</td>
              <td>{{ info.regDate }}</td>
              <td>{{ info.fullName }}</td>
              <td>{{ info.email }}</td>
              <td :style="{ paddingLeft: '30px' }">{{ info.request }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  layout: 'Main',
  data() {
    return {
      hideIcon1: false,
      hideIcon2: false,
      tableHead: [
        'UserID',
        'Registration Date',
        'FullName',
        'Email Address',
        'No of Requests',
      ],
      tableInfo: [
        {
          userID: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          request: 10,
        },
        {
          userID: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          request: 1,
        },
        {
          userID: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          request: 34,
        },
        {
          userID: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          request: 3,
        },
        {
          userID: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          request: 2,
        },
        {
          userID: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          request: 37,
        },
      ],
      showDetail: false,
    }
  },
  methods: {
    hideDateIcon1() {
      this.$refs.fromdate.type = 'date'
      this.hideIcon1 = true
    },
    hideDateIcon2() {
      this.$refs.todate.type = 'date'
      this.hideIcon2 = true
    },
    showDateIcon1() {
      this.$refs.fromdate.type = 'text'
      this.hideIcon1 = false
    },
    showDateIcon2() {
      this.$refs.todate.type = 'text'
      this.hideIcon2 = false
    },
  },
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  margin-left: 3vw;
}
#search-btn {
  background: #f9fafb;
  border: 1px solid #e1edfe;
  box-sizing: border-box;
  border-radius: 8px;
  width: 25vw;
  height: 7.55vh;
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
  width: 12vw;
  height: 7.55vh;
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
  width: 74vw;
  height: 176px;
  left: 286px;
  top: 259px;
  background: #ffffff;
  border-radius: 8px;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  padding: 3vw;
  margin-top: 6.7vh;
}
.search-box {
  position: relative;
}
label {
  display: block;
  padding-bottom: 12px;
}
.green-btn {
  width: 12vw;
  height: 7.5vh;
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
/* table styles start */
.table-div {
  background: #ffffff;
  border-radius: 8px;
  width: 74vw;
  margin-top: 3vh;
  padding: 5vh 0 15vh 0vw;
  align-items: center;
}
.table-top-text {
  font-family: Graphik;
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 15px;
  color: #344563;
  padding: 5vh 0 4vh 3vw;
}
.table-heading {
  background: #f5f8ff;
  padding-left: 3vw;
  background-size: cover;
}
.table-body-row {
  font-family: Graphik;
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
  line-height: 18px;
  display: flex;
  align-items: center;
  padding-left: 3vw;
  color: #6f8a9c;
}

table {
  width: 74vw;
  margin-top: 5px;
}

tr {
  display: flex;
  justify-content: space-between;
  height: 10vh;
  align-items: center;
  padding: 10px 10px 10px 0;
  width: 100%;
  margin: 0;
}

td:last-child {
  border-radius: 0 0 5px 5px;
}

.table-head {
  background: rgba(0, 128, 255, 0.02);
  border-radius: 8px 8px 0 0;
}

th {
  color: #75759e;
}
thead {
  padding: 0;
}
th,
td {
  width: 20%;
  display: flex;
  justify-content: flex-start;
}
.heading {
  padding-bottom: 0vh;
}
@media screen and (min-width: 1400px) {
  .green-btn {
    margin-bottom: 1%;
  }
}
</style>
