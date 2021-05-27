<template>
  <div class="requests">
    <div class="content">
      <div class="top-section">
        <h6>Requests</h6>
        <button class="add-candidate" @click="candidateRegistration = true">
          Add Candidates
        </button>
      </div>
      <div class="filter-search">
        <div class="search-section">
          <p>What are you looking for ?</p>
          <div class="search-container">
            <img src="@/assets/images/search.svg" alt="search" />
            <input
              id="search"
              type="search"
              name="search"
              placeholder="Search ..."
            />
          </div>
        </div>
        <div class="date-container">
          <p>Registration Date</p>
          <div>
            <input id="from-date" type="date" name="date" />
            <input id="to-date" type="date" name="date" />
            <button class="refine-search">Refine Search</button>
          </div>
        </div>
      </div>
      <table>
        <div class="table-top">
          <p class="table-top-text">All Requests (1028)</p>
        </div>
        <tr class="table-head">
          <th class="user td-th">User ID</th>
          <th class="request-date td-th">Requests Date</th>
          <th class="full-name td-th">Full Name</th>
          <th class="email td-th">Email Address</th>
          <th class="td-th">Category</th>
        </tr>
        <tr
          v-for="el in tableElements"
          :key="el.userId"
          class="table-body"
          @click="requestDetails = true"
        >
          <td class="user td-th">{{ el.userId }}</td>
          <td class="request-date td-th">{{ el.requestDate }}</td>
          <td class="full-name td-th">{{ el.fullName }}</td>
          <td class="email td-th">{{ el.email }}</td>
          <td class="category td-th">
            {{ el.category }}
          </td>
        </tr>
      </table>
    </div>
    <RequestDetails
      v-show="requestDetails"
      @close-requestDetails="requestDetails = false"
    />
  </div>
</template>

<script>
import RequestDetails from '@/components/Modals/RequestDetails.vue'
export default {
  components: {
    RequestDetails,
  },
  layout: 'Main',
  data() {
    return {
      requestDetails: false,
      tableElements: [
        {
          userId: 'ND1283',
          requestDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          category: 'Chef',
        },
        {
          userId: 'ND1283',
          requestDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          category: 'Driver',
        },
        {
          userId: 'ND1283',
          requestDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          category: 'Cleaner',
        },
        {
          userId: 'ND1283',
          requestDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          category: 'Dry Cleaner',
        },
        {
          userId: 'ND1283',
          requestDate: '23.04.2020',
          fullName: 'Abdul Ifeoma',
          email: 'amaranth@outlook.com',
          category: 'Butler',
        },
        {
          userId: 'ND1283',
          requestDate: '23.04.2020',
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
.requests {
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

.filter-search {
  display: flex;
  justify-content: space-between;
  background-color: white;
  padding: 25px 43px;
}

.search-section {
  flex-basis: 33%;
}

.filter-search p {
  font-size: 15px;
  color: black;
}

.search-container {
  display: flex;
  align-content: center;
  border: 1px solid #e1edfe;
  border-radius: 8px;
  background-color: #f9fafb;
  width: 100%;
  padding: 13px 16px;
  margin-top: 13px;
  margin-right: 13px;
}

#search {
  outline: none;
  border: none;
  background-color: transparent;
  margin-left: 19px;
  width: 200px;
}

#from-date,
#to-date {
  width: 167px;
  padding: 11px 16px;
  margin-top: 13px;
  border: 1px solid #e1edfe;
  border-radius: 8px;
  background-color: #f9fafb;
  margin-right: 24px;
}

#from-date ::placeholder {
  font-size: 15px;
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
</style>
