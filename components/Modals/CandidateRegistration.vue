<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div class="content">
        <h6>Candidates Registration</h6>
        <div class="tabs">
          <div
            :class="
              activeTab.includes('personal-details') ? 'active' : 'inactive'
            "
            class="personal-details"
            @click="activeTab = 'personal-details'"
          >
            Personal Details
          </div>
          <div
            :class="
              activeTab.includes('reports-upload') ? 'active' : 'inactive'
            "
            class="reports-upload"
            @click="activeTab = 'reports-upload'"
          >
            Reports Upload
          </div>
        </div>
        <div
          v-show="activeTab == 'personal-details'"
          class="tab-1 personal-details"
        >
          <div class="form">
            <div class="form-container">
              <div>
                <p>First Name</p>
                <input id="first-name" type="text" name="first-name" />
              </div>
              <div class="inner-div">
                <div>
                  <p>ID Number</p>
                  <input id="id-num" type="text" name="id-num" />
                </div>
                <div>
                  <p>Category</p>
                  <input id="category" type="text" name="category" />
                </div>
              </div>
              <div>
                <p>Origin</p>
                <input id="origin" type="text" name="origin" />
              </div>
              <div>
                <p>Unique Skill(s)</p>
                <textarea id="skills" type="text" cols="40" rows="5"></textarea>
              </div>
              <div>
                <p>History</p>
                <textarea
                  id="history"
                  type="text"
                  cols="30"
                  rows="5"
                ></textarea>
              </div>
            </div>
            <div class="form-container">
              <div>
                <p>Last Name</p>
                <input id="last-name" type="text" name="last-name" />
              </div>
              <div class="inner-div">
                <div>
                  <p>Age</p>
                  <input id="age" type="text" name="age" />
                </div>
                <div>
                  <p>Availability</p>
                  <input id="availability" type="text" name="availability" />
                </div>
              </div>
              <div class="inner-div">
                <div>
                  <p>Gender</p>
                  <input id="gender" type="text" name="gender" />
                </div>
                <div>
                  <p>Experiences</p>
                  <input id="experiences" type="text" name="experiences" />
                </div>
              </div>
              <div>
                <p>Residence</p>
                <textarea
                  id="residence"
                  type="text"
                  cols="30"
                  rows="12"
                ></textarea>
              </div>
            </div>
          </div>
          <div class="bottom-btn">
            <button>Save</button>
            <p>Delete</p>
          </div>
        </div>
        <div v-show="activeTab == 'reports-upload'" class="tab-2">
          <ReportsUploads />
        </div>
      </div>
    </div>
    <div class="close" @click="$emit('close-candidateRegistration')">
      <img src="@/assets/images/close.svg" alt="close" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeTab: 'personal-details',
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
  width: 1067px;
  border-radius: 8px;
}

.close {
  margin-top: 10%;
  margin-left: 16px;
  cursor: pointer;
}

.content {
  width: 85%;
  margin: 80px 80px;
}

.content h6 {
  font-size: 25px;
  font-weight: 500;
  color: black;
  margin-bottom: 42px;
}

.tabs {
  background-color: #f9fafb;
  display: flex;
  width: 500px;
  border-radius: 8px;
  margin-bottom: 60px;
}

.personal-details {
  border-radius: 8px 0 0 8px;
}
.reports-upload {
  border-radius: 0 8px 8px 0;
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
  background-color: #00a69d !important;
  color: white;
}

.active {
  background-color: #00a69d !important;
  color: white;
}

/* FORM  */

.form {
  display: flex;
  justify-content: space-between;
}

.form-container {
  flex-basis: 50%;
  margin-right: 20px;
}

.form-container p {
  font-size: 14px;
  margin-bottom: 10px;
}

.form-container input {
  height: 50px;
  width: 100%;
  margin-bottom: 20px;
}

.inner-div {
  display: flex;
  justify-content: space-between;
}

.inner-div input {
  width: 200px;
  margin-bottom: 20px;
  padding: 0 10px;
}

input,
textarea {
  border: 1px solid #d1d1d1;
  border-radius: 8px;
}

textarea {
  width: 100%;
}

button {
  background-color: #00a69d;
  border: none;
  border-radius: 8px;
  color: white;
  padding: 14px 61px;
  cursor: pointer;
}

.bottom-btn {
  display: flex;
  margin-top: 80px;
  align-items: center;
}

.bottom-btn p {
  margin-left: 60px;
  cursor: pointer;
}
</style>
