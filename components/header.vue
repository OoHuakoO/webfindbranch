<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <b-navbar-nav>
        <nuxt-link class="nav-item nav-link" to="/">หน้าแรก</nuxt-link>
      </b-navbar-nav>
     
    </b-navbar>
  </div>
</template>
<style scoped>
* {
  font-family: 'Sukhumvit';
}
.navbar.navbar-dark.bg-dark {
  background-color: #002447 !important;
}
.navbar-dark .navbar-nav .nav-link {
  color: #53d3d1;
  font-size: 2vw;
}
img {
  margin-right: 0.5vw;
  width: 2vw;
  margin-bottom: 2%;
}
@media screen and (max-width: 1150px) {
  .navbar-dark .navbar-nav .nav-link {
    font-size: 3vw;
  }
  img {
    margin-right: 0.5vw;
    width: 3vw;
    margin-bottom: 2%;
  }
}
@media screen and (max-width: 716px) {
  .navbar-dark .navbar-nav .nav-link {
    font-size: 4vw;
  }
  img {
    margin-right: 0.5vw;
    width: 4vw;
    margin-bottom: 2%;
  }
}
</style>
