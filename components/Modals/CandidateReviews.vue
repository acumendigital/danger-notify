<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div class="content">
        <div class="top-section">
          <h6>Abdul Ifeoma</h6>
          <p class="job">Chef</p>
          <div class="review-sort">
            <div>
              <span class="rating-number">5.0</span
              ><img src="@/assets/images/Star.svg" alt="rate" /><span
                class="review-number"
                >7 Reviews</span
              >
            </div>
            <div class="sort-by">
              <div>
                <span class="sort">Sort by:</span
                ><span class="sort-options">Most relevant</span>
              </div>
              <img
                src="@/assets/images/icon/navigation/arrow_drop_down_24px.svg"
                alt=""
              />
            </div>
          </div>
        </div>
        <div class="section">
          <div class="reviews">
            <div>
              <img src="@/assets/images/profile-image50x50.svg" alt="" />
              <div>
                <p class="reviewers-name">Akande Oluwaseun</p>
                <p class="reviewers-number">2 Reviews</p>
                <p class="reviewers-review">
                  Very Punctual And attentive to the difference in my taste of
                  Food. A real Cook I must say.
                </p>
                <button>Reply</button>
              </div>
            </div>
            <div class="review-menu-container">
              <img
                class="review-menu"
                src="@/assets/images/menu 2.svg"
                alt=""
                @click="reviewOptions = !reviewOptions"
              />
              <div v-show="reviewOptions" class="review-options">
                <p>Approve</p>
                <p>Delete</p>
              </div>
            </div>
          </div>
          <div class="reviews">
            <div>
              <img src="@/assets/images/profile-image50x50.svg" alt="" />
              <div>
                <p class="reviewers-name">Akande Oluwaseun</p>
                <p class="reviewers-number">2 Reviews</p>
                <p class="reviewers-review">
                  Very Punctual And attentive to the difference in my taste of
                  Food. A real Cook I must say.
                </p>
                <button>Reply</button>
              </div>
            </div>
            <div class="review-menu-container">
              <img
                class="review-menu"
                src="@/assets/images/menu 2.svg"
                alt=""
                @click="reviewOptions = !reviewOptions"
              />
              <div v-show="reviewOptions" class="review-options">
                <p>Approve</p>
                <p>Delete</p>
              </div>
            </div>
          </div>
          <div class="reviews">
            <div>
              <img src="@/assets/images/profile-image50x50.svg" alt="" />
              <div>
                <p class="reviewers-name">Akande Oluwaseun</p>
                <p class="reviewers-number">2 Reviews</p>
                <p class="reviewers-review">
                  Very Punctual And attentive to the difference in my taste of
                  Food. A real Cook I must say.
                </p>
                <button>Reply</button>
              </div>
            </div>
            <div class="review-menu-container">
              <img
                class="review-menu"
                src="@/assets/images/menu 2.svg"
                alt=""
                @click="reviewOptions = !reviewOptions"
              />
              <div v-show="reviewOptions" class="review-options">
                <p>Approve</p>
                <p>Delete</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="close" @click="$emit('close-candidateReview')">
      <img src="@/assets/images/close.svg" alt="close" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      reviewOptions: false,
    }
  },
}
</script>

<style scoped>
.modal-backdrop {
  position: fixed;
  background-color: rgba(24, 18, 46, 0.8);
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  align-items: flex-start;
}

.modal {
  margin: 4% 0;
  background-color: white;
  width: 867px;
  border-radius: 8px;
  height: 699px;
  overflow-y: auto;
}

.close {
  margin-top: 4%;
  margin-left: 16px;
  cursor: pointer;
}
.content {
  width: 100%;
  padding: 80px 100px;
}

/* TOP SECTION  */

.top-section {
  padding-left: 30px;
  margin-bottom: 35px;
}

h6 {
  font-size: 24px;
  font-weight: 500;
  color: black;
}

.job {
  font-size: 18px;
  margin: 12px 0;
}

.review-sort {
  display: flex;
  justify-content: space-between;
}
.rating-number {
  font-size: 16px;
  color: black;
  margin-right: 4px;
}

.review-number {
  font-size: 14px;
  color: #717f88;
  margin-left: 10px;
}

.sort-by {
  display: flex;
  align-items: center;
}

.sort-by div {
  margin-right: 13px;
}

.sort {
  font-weight: 600;
  margin-right: 5px;
  color: #042538;
}

.sort-options {
  color: #042538;
}

/* MAIN SECTION  */

.section {
  overflow-y: auto;
}

.reviews {
  border-top: 1px solid #dadada;
  border-bottom: 1px solid #dadada;
  padding: 45px;
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
}

.reviews > div {
  display: flex;
  align-items: flex-start;
}

.reviews > div > div {
  margin-left: 15px;
}

.reviewers-name {
  color: black;
  font-size: 18px;
  font-weight: 600;
}

.reviewers-number {
  font-size: 14px;
  color: #717f88;
  margin: 10px 0;
}

.reviewers-review {
  color: #717f88;
  font-size: 14px;
  width: 358px;
}

.review-menu {
  cursor: pointer;
}

button {
  outline: none;
  border: none;
  background-color: transparent;
  color: #042538;
  font-size: 14px;
  margin-top: 10px;
  cursor: pointer;
}

.review-menu-container {
  position: relative;
}

.review-options {
  position: absolute;
  right: 70%;
  top: 60%;
  border: 1px solid #c4cdd5;
  background-color: whitex;
  border-radius: 8px;
  padding: 20px 30px;
  width: 154px;
}

.review-options p {
  font-size: 14px;
  color: #042538;
  padding: 8px 0;
  cursor: pointer;
}
</style>
