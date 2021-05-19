<template>
  <div class="side-menu">
    <div class="content">
      <nuxt-link to="/"
        ><div class="menu">
          <img src="@/assets/images/home.svg" alt="home" />
          <p>Dashboard</p>
        </div></nuxt-link
      >
      <nuxt-link to="/Customers"
        ><div class="menu">
          <img src="@/assets/images/customer.svg" alt="home" />
          <p>Customers</p>
        </div></nuxt-link
      >
      <nuxt-link to="/Candidates"
        ><div class="menu">
          <img src="@/assets/images/candidate.svg" alt="home" />
          <p>Candidates</p>
        </div></nuxt-link
      >
      <nuxt-link to="/Requests"
        ><div class="menu">
          <img src="@/assets/images/interview.svg" alt="home" />
          <p>Requests</p>
        </div></nuxt-link
      >
      <nuxt-link to="/Payment"
        ><div class="menu">
          <img src="@/assets/images/credit-card.svg" alt="home" />
          <p>Payment</p>
        </div></nuxt-link
      >
      <nuxt-link to="/Reviews"
        ><div class="menu">
          <img src="@/assets/images/evaluate.svg" alt="home" />
          <p>Reviews</p>
        </div></nuxt-link
      >
      <nuxt-link to="/Settings"
        ><div class="menu">
          <img src="@/assets/images/settings.svg" alt="home" />
          <p>Settings</p>
        </div></nuxt-link
      >
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.side-menu {
  position: fixed;
  width: 245px;
  height: 900px;
  background-color: white;
  padding-top: 74px;
}

.menu {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
  height: 60px;
  cursor: pointer;
}

.menu img {
  padding: 20px 20px 20px 32px;
}

.menu p {
  color: #6f8a9c;
  width: 100%;
  padding: 21px 16px;
}

a.nuxt-link-exact-active .menu,
a:hover .menu {
  background-color: rgba(4, 37, 56, 0.076);
}

a.nuxt-link-exact-active p,
a:hover p {
  color: #010025;
  font-weight: 600;
}

a.nuxt-link-exact-active img,
a:hover img {
  background-color: #010025;
  border-radius: 0 20px 20px 0;
}
</style>
