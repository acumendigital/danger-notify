<template>
  <div>
    <div class="contacts">
      <button class="saved">
        <img
          class="left-arrow"
          src="~assets/image/vector.png"
          @click="$router.go(-1)"
        />
        Saved Contacts
        <img class="plus" src="~assets/image/plus.png" />
      </button>
    </div>
    <p class="email">
      Contacts here would receive your emergency alerts via sms or email.
    </p>
    <div class="names">
      <Contact
        v-for="(contact, index) in contacts"
        :key="index"
        :contact="contact"
      />
    </div>
    <div class="link">
      <nuxt-link to="/newContact"
        ><img class="pluss" src="~assets/image/plus.png" />Add
        Contact</nuxt-link
      >
    </div>
  </div>
</template>
<script>
import Contact from '@/components/Contact.vue'
export default {
  components: {
    Contact,
  },
  layout: 'bottomMenu',
  data: () => ({
    contacts: [
      {
        image: 'download_1.png',
        name: 'Dad',
        phone: '+2348108551935',
      },
      {
        image: 'download_1.png',
        name: 'Mum',
        phone: '+2348108551935',
      },
      {
        image: 'download_1.png',
        name: 'Victor',
        phone: '+2348108551935',
      },
      {
        image: 'download_1.png',
        name: 'Katherine',
        phone: '+2348108551935',
      },
    ],
  }),
}
</script>
<style scoped>
.saved {
  background-color: white;
  border: none;
  box-shadow: 0 4px 8px 0 rgba(107, 107, 107, 0.2),
    0 6px 20px 0 rgba(131, 130, 130, 0.19);
  width: 345px;
  height: 60px;
  border-radius: 12px;
  margin: auto;
  margin-top: 30px;
  color: black;
  font-weight: 600;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0px 10px;
}
.contacts {
  text-align: center;
}
.email {
  text-align: start;
  font-size: 16px;
  font-weight: 300;
  color: black;
  margin-left: 40px;
  margin-right: 30px;
  margin-top: 35px;
}

.names {
  text-align: center;
}
.left-arrow {
  width: 10px;
}
.plus {
  width: 20px;
}
a {
  color: #990c0c;
}
.link {
  text-align: center;
  margin-top: 35px;
}
.pluss {
  width: 15px;
  margin-right: 15px;
}
</style>
