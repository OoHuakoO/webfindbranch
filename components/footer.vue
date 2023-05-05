<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <span>
      
      </span>
    </b-navbar>
  </div>
</template>
<style scoped>
* {
  font-family: 'Sukhumvit';
}
span {
  color: white;
  font-weight: 100;
  margin: 0px;
  font-size: 1vw;
  opacity: 0.7;
}
.navbar.navbar-dark.bg-dark {
  background-color: #072f4f !important;
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
}

@media screen and (max-width: 1150px) {
  span {
    font-size: 1.5vw;
  }
}
@media screen and (max-width: 716px) {
  span {
    font-size: 1.2vw;
  }
  .navbar.navbar-dark.bg-dark {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 20px;
  }
}
</style>
