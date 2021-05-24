<template>
  <div class="modal-backdrop">
    <span class="close" @click="closeModal">X</span>
    <div class="modal">
      <h2>Customers Detail</h2>
      <div class="first-row">
        <div
          class="green"
          :class="{ basictab: showBasicDetail }"
          @click="showBasic"
        >
          Basic Details
        </div>
        <div
          class="fulltab"
          :class="{ white: showFullDetail }"
          @click="showFull"
        >
          Full Details
        </div>
      </div>
      <div v-if="showBasicDetail" class="sec-row">
        <div class="full">
          <p v-for="head in heading1" :key="head" class="value">{{ head }}</p>
        </div>

        <div class="full">
          <p v-for="value in values1" :key="value" class="value">{{ value }}</p>
        </div>
      </div>
      <div v-else class="full-sec-row">
        <div class="link-tabs">
          <nav class="tabs">
            <button
              v-for="(tab, index) in tab_item"
              :key="index"
              class="tabs__item"
              :class="{
                'tabs__item_active:focus': currentTab === index,
                first_active: justLoaded,
              }"
              @click="currentTab = index"
            >
              {{ tab }}
            </button>
          </nav>
        </div>
        <div class="content-container">
          <div v-if="currentTab === 0" class="active">
            <div v-for="head in heading2" :key="head" class="active-tab">
              <div class="left-value">
                <p v-for="key in tableKey" :key="key" class="value">
                  {{ key }}:
                </p>
              </div>
              <div class="right-value">
                <p class="value">
                  {{ head.candidate_name }}
                </p>
                <p class="value">
                  {{ head.hire_date }}
                </p>
                <p class="value">
                  {{ head.hire_type }}
                </p>
                <p class="value">
                  {{ head.category }}
                </p>
              </div>
            </div>
          </div>
          <div v-if="currentTab === 1" class="pending">
            <div v-for="head in heading2" :key="head" class="pending-tab">
              <div class="left-value">
                <p v-for="key in tableKey" :key="key" class="value">
                  {{ key }}:
                </p>
                <p class="value green-btn" role="button">Accept</p>
              </div>
              <div class="right-value">
                <p class="value">
                  {{ head.candidate_name }}
                </p>
                <p class="value">
                  {{ head.hire_date }}
                </p>
                <p class="value">
                  {{ head.hire_type }}
                </p>
                <p class="value">
                  {{ head.category }}
                </p>
                <p class="value">Decline</p>
                <div class="spacer"></div>
              </div>
            </div>
          </div>
          <div v-if="currentTab === 2" class="completed">
            <div v-for="head in heading3" :key="head" class="completed-tab">
              <div class="left-value">
                <p v-for="key in tableKey2" :key="key" class="value">
                  {{ key }}:
                </p>
              </div>
              <div class="right-value">
                <p class="value">
                  {{ head.candidate_name }}
                </p>
                <p class="value">
                  {{ head.hire_date }}
                </p>
                <p class="value">
                  {{ head.hire_type }}
                </p>
                <p class="value">
                  {{ head.category }}
                </p>
                <p class="value">
                  {{ head.subscription_type }}
                </p>
                <p class="value">
                  {{ head.end_date }}
                </p>
                <div class="spacer"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Review',
  data() {
    return {
      showBasicDetail: '',
      showFullDetail: false,
      currentTab: 0,
      heading1: [
        'Fullname',
        'Email',
        'Phone Number',
        'Pending Requests',
        'Active Requests',
        'Completed Requests',
      ],
      values1: [
        'Precious Makinde',
        'precious@makindeorg.com',
        '+44 829 9015 2482',
        56,
        82,
        94,
      ],
      tab_item: ['Active Requests', 'Pending Requests', 'Completed Requests'],
      heading2: [
        {
          candidate_name: 'Precious Makinde',
          hire_date: '10.10.2019',
          hire_type: 'Fulltime Engagement',
          category: 'Chef',
          subscription_type: 'Quaterly',
          end_date: '10.10.2019',
        },
        {
          candidate_name: 'Precious Makinde',
          hire_date: '10.10.2019',
          hire_type: 'Fulltime Engagement',
          category: 'Chef',
        },
        {
          candidate_name: 'Precious Makinde',
          hire_date: '10.10.2019',
          hire_type: 'Fulltime Engagement',
          category: 'Chef',
        },
      ],
      heading3: [
        {
          candidate_name: 'Precious Makinde',
          hire_date: '10.10.2019',
          hire_type: 'Fulltime Engagement',
          category: 'Chef',
          subscription_type: 'Quaterly',
          end_date: '10.10.2019',
        },
        {
          candidate_name: 'Precious Makinde',
          hire_date: '10.10.2019',
          hire_type: 'Fulltime Engagement',
          category: 'Chef',
          subscription_type: 'Quaterly',
          end_date: '10.10.2019',
        },
      ],
      tableKey: ['Candidate Name', 'Hire Date', 'Hire Type', 'Category'],
      tableKey2: [
        'Candidate Name',
        'Hire Date',
        'Hire Type',
        'Category',
        'Subscription Type',
        'End Date',
      ],
    }
  },
  mounted() {
    this.showBasicDetail = true
  },
  methods: {
    showBasic() {
      this.showBasicDetail = true
      this.showFullDetail = false
    },
    showFull() {
      this.showBasicDetail = false
      this.showFullDetail = true
      this.currentTab = 0
    },
    closeModal() {
      this.$emit('close')
    },
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
  background: rgba(24, 18, 46, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Overpass', sans-serif;
  overflow-y: auto;
  z-index: 3;
  padding: 50px 0;
}

.modal {
  background: #ffffff;
  margin: auto;
  overflow-y: auto;
  display: flex;
  flex-direction: column;
  border-radius: 8px;
  width: 46vw;
  padding: 60px 0 8vh 101px;
  height: 90vh;
}

button {
  cursor: pointer;
  outline: none;
}

.modal > h2 {
  font-family: Graphik;
  font-style: normal;
  font-weight: 500;
  font-size: 32px;
  line-height: 1%;
  display: flex;
  align-items: center;
  color: #000000;
  margin: 0px 0 52px 0px;
  text-align: left;
}

.first-row {
  display: flex;
  flex-direction: row;
  justify-content: center;
  width: 30vw;
  height: 50px;
  background: #f9fafb;
  border: 1px solid #e1edfe;
  border-radius: 8px;
  cursor: default;
}
.green {
  border-right: 0.5px black;
  flex-basis: 50%;
  text-align: center;
  align-items: center;
  padding-top: 18px;
}
.basictab {
  background-color: #00a69d;
  flex-basis: 50%;
  text-align: center;
  padding-top: 15px;
  padding-bottom: 7px;
  border-radius: 8px 0 0 8px;
  height: 50px;
  box-sizing: border-box;
  color: white;
}
.white {
  background-color: #00a69d;
  flex-basis: 50%;
  text-align: center;
  padding-top: 20px;
  padding-bottom: 3px;
  border-radius: 0px 8px 8px 0px;
  height: 50px;
  box-sizing: border-box;
  color: white;
}
.fulltab {
  border-right: 0.5px black;
  flex-basis: 50%;
  text-align: center;
  align-items: center;
  padding-top: 15px;
  padding-bottom: 7px;
  box-sizing: border-box;
}
.sec-row {
  display: flex;
  flex-direction: row;
  /* justify-content: space-around; */
  margin-top: 6vh;
  text-align: left;
}
.full {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  text-align: left;
  padding-right: 2vw;
}
.value {
  padding: 2.5vh 0;
  font-family: Graphik;
  font-style: normal;
  font-weight: 600;
  font-size: 16px;
  line-height: 18px;

  color: #717f88;
  text-align: left;
}

/* full details tab */

.tabs__item_active {
  color: #00a69d;
  border-bottom: 1px solid #00a69d;
}

.tabs__item:hover {
  color: #00a69d;
  border-bottom: 1px solid #00a69d;
}

.tabs__item:focus {
  color: #00a69d;
  border-bottom: 1px solid #00a69d;
  outline: none;
  z-index: 2;
}

.tabs__item {
  display: inline-block;
  margin-right: 0.5vw;
  padding: 7px;
  padding-bottom: 8px;
  font-size: 16px;
  color: #30425a;
  z-index: 2;
  text-decoration: none;
  border: none;
  background-color: transparent;
  border-bottom: 1px solid #e4e4e4;
  cursor: pointer;
  transition: all 0.25s;
}
.tabs__active-line {
  position: absolute;
  bottom: 0;
  left: 0;
  height: 2px;
  background-color: black;
  transition: transform 0.4s ease, width 0.4s ease;
}
.active-tab,
.pending-tab,
.completed-tab {
  display: flex;
  flex-direction: row;
}
.full-sec-row {
  display: flex;
  flex-direction: column;
  text-align: left;
  margin-top: 6vh;
}
.left-value {
  margin-right: 3vw;
}
.content-container {
  /* margin-top: 3vh; */
  padding-bottom: 6vh;
  position: relative;
}

/* pending request styles */

.green-btn {
  width: 12vw;
  height: 7.55vh;
  background: #00a69d;
  border-radius: 8px;
  display: inline-block;
  margin-top: 3%;
  padding-top: 2.5vh;
  padding-bottom: auto;
  color: #ffffff;
  font-family: Graphik;
  font-style: normal;
  font-weight: 500;
  font-size: 13px;
  line-height: 14px;
  text-align: center;
  cursor: pointer;
}
.spacer {
  height: 3vh;
}
.close {
  position: absolute;
  width: 26px;
  height: 26px;
  left: 75vw;
  top: 8.5vh;
  border-radius: 50%;
  background: rgba(0, 166, 157, 0.25);
  padding: 6px 3px 6px 8.5px;
  cursor: pointer;
}
.active-tab,
.pending-tab,
.completed-tab {
  border-bottom: 1.5px solid #e4e4e4;
  width: 90%;
  margin-top: 3vh;
  padding-bottom: 2vh;
}
.active-tab:nth-last-child(1),
.pending-tab:nth-last-child(1),
.completed-tab:nth-last-child(1) {
  border-bottom: none;
}
/* .tabs button:nth-child(1) {
  color: #00a69d;
  border-bottom: 1px solid #00a69d;
} */
</style>
