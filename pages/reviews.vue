<template>
  <div class="candidate">
    <div class="content">
      <div class="top-section">
        <h6>Reviews</h6>
        <button class="add-candidate" @click="candidateReview = true">
          Add Reviews
        </button>
      </div>
      <div class="filter-search">
        <div>
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
          <p class="table-top-text">All Reviews (1028)</p>
        </div>
        <tr class="table-head">
          <th class="user td-th">User ID</th>
          <th class="full-name td-th">Full Name</th>
          <th class="email td-th">Email Address</th>
          <th class="category td-th">Category</th>
          <th class="review td-th">Reviews</th>
        </tr>
        <tr
          v-for="el in tableElements"
          :key="el.userId"
          class="table-body"
          @click="candidateDetails = true"
        >
          <td class="user td-th">{{ el.userId }}</td>
          <td class="full-name td-th">{{ el.fullName }}</td>
          <td class="email td-th">{{ el.email }}</td>
          <td class="category td-th">
            {{ el.category }}
          </td>
          <td class="review td-th">{{ el.review }}</td>
        </tr>
      </table>
    </div>
    <CandidateReviews
      v-show="candidateReview"
      @close-candidateReview="candidateReview = false"
    />
  </div>
</template>

<script>
import CandidateReviews from '@/components/Modals/CandidateReviews.vue'
export default {
  components: {
    CandidateReviews,
  },
  layout: 'Main',
  data() {
    return {
      candidateReview: false,
      tableElements: [
        {
          userId: 'ND1283',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          category: 'Chef',
          review: 'Very punctual and attentive to instru....',
        },
        {
          userId: 'ND1283',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          category: 'Driver',
          review: 'Very punctual and attentive to instru....',
        },
        {
          userId: 'ND1283',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          category: 'Cleaner',
          review: 'Very punctual and attentive to instru....',
        },
        {
          userId: 'ND1283',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          category: 'Dry Cleaner',
          review: 'Very punctual and attentive to instru....',
        },
        {
          userId: 'ND1283',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          category: 'Baby Sitter',
          review: 'Very punctual and attentive to instru....',
        },
        {
          userId: 'ND1283',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          category: 'Driver',
          review: 'Very punctual and attentive to instru....',
        },
      ],
    }
  },
}
</script>

<style scoped>
.candidate {
  padding: 70px 41px;
  width: 100%;
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
  background-color: white;
  padding: 25px 43px;
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
  width: 384px;
  padding: 13px 16px;
  margin-top: 13px;
  margin-right: 13px;
}

#search {
  outline: none;
  border: none;
  background-color: transparent;
  margin-left: 19px;
  width: 300px;
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
  width: 15%;
}

.review {
  width: 40%;
}
</style>
