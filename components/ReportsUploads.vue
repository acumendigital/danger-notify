<template>
  <div>
    <div class="content">
      <div class="upload-section">
        <img src="@/assets/images/upload.svg" alt="img" />
        <p class="upload-title">Medical Profile and History</p>
        <p class="upload-subtext">
          Drag and drop file here or just
          <span class="upload-link">browse</span> file
        </p>
      </div>
      <div class="section-2">
        <div>
          <input id="checkbox" type="checkbox" name="medical-profile" />
          <span>Medical Profile and History</span>
        </div>
        <div>
          <input id="checkbox" type="checkbox" name="medical-profile" /><span
            >Clinical Records</span
          >
        </div>
        <div>
          <input id="checkbox" type="checkbox" name="medical-profile" /><span
            >Residential Address Verification</span
          >
        </div>
        <div>
          <input id="checkbox" type="checkbox" name="medical-profile" /><span
            >Work History Verification</span
          >
        </div>
        <div>
          <input id="checkbox" type="checkbox" name="medical-profile" /><span
            >Guarantors Profile Verification</span
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.content {
  display: flex;
}

/* UPLOAD SECTION  */

.upload-section {
  width: 55%;
  text-align: center;
  padding: 120px 0;
  border: 0.5px dashed #c4c4c4;
}

.upload-section img {
  margin-bottom: 25px;
}

.upload-title {
  font-size: 15px;
  font-weight: 600;
  color: #0e1127;
  margin-bottom: 15px;
}

.upload-subtext {
  font-size: 15px;
  width: 220px;
  margin: auto;
}

.upload-link {
  color: #00a69d;
  font-weight: 600;
  cursor: pointer;
}

/* SECTION-2  */

.section-2 {
  padding: 20px 45px;
  width: 45%;
}

.section-2 div {
  display: flex;
  align-items: center;
  margin-bottom: 30px;
}

#checkbox {
  height: 30px;
  width: 30px;
  margin-right: 12px;
}
</style>
