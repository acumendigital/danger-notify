<template>
  <div class="candidate">
    <div class="content">
      <div class="top-section">
        <h6>Candidates</h6>
        <button class="add-candidate" @click="candidateRegistration = true">
          Add Candidates
        </button>
        <button class="add-candidate" @click="candidateDetails = true">
          Add Candidates
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
</style>
