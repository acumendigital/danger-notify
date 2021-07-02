<template>
  <div class="number" @click="$router.push('/editContact')">
    <div class="image-container">
      <img class="user" src="~assets/image/download_1.png" />
      <div class="text-container">
        <span class="contact-name">{{ contact.name }}</span>
        <small>{{ contact.phone }}</small>
      </div>
    </div>
    <img class="right-arrow" src="~assets/image/vector-2.png" />
  </div>
</template>

<script>
export default {
  props: {
    contact: {
      type: Object,
      required: true,
      default: Object,
    },
  },
}
</script>

<style>
.number {
  background-color: white;
  border: none;
  box-shadow: 0 4px 8px 0 rgba(107, 107, 107, 0.2),
    0 6px 20px 0 rgba(131, 130, 130, 0.19);
  width: 335px;
  height: 80px;
  border-radius: 12px;
  margin: auto;
  margin-top: 30px;
  color: black;
  font-weight: 600;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 10px;
}
.image-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 57%;
}
.text-container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.text-container small {
  font-size: 12px;
  color: black;
}
.user {
  border-radius: 50%;
  width: 60px;
}
.right-arrow {
  width: 10px;
}
.contact-name {
  color: black;
}
</style>
