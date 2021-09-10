<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <b-navbar-nav>
        <nuxt-link class="nav-item nav-link" to="/">หน้าแรก</nuxt-link>
      </b-navbar-nav>
      <b-navbar-nav class="ml-auto">
        <nuxt-link class="nav-item nav-link" to="/organizer">
          <b-img src="~assets/Alert.svg" fluld />เกี่ยวกับผู้จัดทำ</nuxt-link
        >
      </b-navbar-nav>
    </b-navbar>
  </div>
</template>
<style scoped>
.navbar.navbar-dark.bg-dark {
  background-color: #002447 !important;
}
.navbar-dark .navbar-nav .nav-link {
  color: #53d3d1;
  font-size: 30px;
  font-family: 'Sukhumvit';
}
img {
  margin-right: 10px;
  width: 30px;
  margin-bottom: 3px;
}
</style>
