<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div class="content">
        <h6>Candidate Details</h6>
        <div class="candidate-details">
          <div class="details-container">
            <p class="title">User ID:</p>
            <p class="detail">HE55778</p>
          </div>
          <div class="details-container">
            <p class="title">Fullname::</p>
            <p class="detail">Precious Makinde</p>
          </div>
          <div class="details-container">
            <p class="title">Category:</p>
            <p class="detail">Female</p>
          </div>
          <div class="details-container">
            <p class="title">Payment Date:</p>
            <p class="detail">2 Years +</p>
          </div>
          <div class="details-container">
            <p class="title">Payment Package:</p>
            <p class="detail">Annual</p>
          </div>
          <div class="details-container">
            <p class="title">Email:</p>
            <p class="detail">precious@makindeorg.com</p>
          </div>
        </div>
        <div class="bottom-btn">
          <input id="download" type="button" value="Download" />
          <input id="delete" type="button" value="Delete" />
        </div>
      </div>
    </div>
    <div class="close" @click="$emit('close-paymentDetails')">
      <img src="@/assets/images/close.svg" alt="close" />
    </div>
  </div>
</template>

<script>
export default {}
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
}

.modal {
  margin-top: 6%;
  background-color: white;
  width: 698px;
  border-radius: 8px;
  height: 650px;
  overflow-y: auto;
}

.close {
  margin-top: 6%;
  margin-left: 16px;
  cursor: pointer;
}

.content {
  width: 75%;
  margin: 80px 80px;
}

.content h6 {
  font-size: 25px;
  font-weight: 500;
  color: black;
  margin-bottom: 42px;
}

/* CANDIDATE DETAILS  */

.details-container {
  display: flex;
  margin-bottom: 30px;
}

.title {
  font-size: 16px;
  color: #767676;
  flex-basis: 35%;
}

.detail {
  font-weight: 600;
  flex-basis: 65%;
}

.bottom-btn {
  margin-top: 70px;
}

#download {
  color: white;
  background-color: #00a69d;
  padding: 15px 80px;
  border: none;
  border-radius: 8px;
}

#delete {
  background-color: transparent;
  border: none;
  color: #717f88;
  margin-left: 30px;
}
</style>
