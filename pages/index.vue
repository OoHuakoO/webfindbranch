<template>
  <div class="body">
    <Header />

    <div class="bigContainer">
      <b-img src="~assets/banner.svg" fluld />
      <p class="title">กิจกรรมค้นหาวิชาสาขาสำหรับคุณ</p>
      <p class="subtitle">
        โปรดเลือกสิ่งที่คุณสนใจ มีทักษะ หรือชื่นชอบ <br />
        เพื่อรับชมวิดีโอของสาขาวิชาที่เหมาะกับคุณ <br />
        ผ่านแบบสอบถามสั้น ๆ ต่อไปนี้
      </p>
      <nuxt-link class="btn-link" to="/selectChoice">
        <b-button>เริ่มทำแบบสอบถาม</b-button>
      </nuxt-link>
    </div>
  </div>
</template>
<script>
import Header from '@/components/header'
export default {
  components: {
    Header,
  },
}
</script>
<style scoped>
* {
  font-family: 'Sukhumvit';
}
html,
.body {
  min-height: 100%;
}
.bigContainer {
  justify-content: center;
  align-items: center;
  padding: 10vw;
  display: flex;
  flex-direction: column;
}
.title {
  font-weight: bold;
  font-size: 5vw;
  text-align: center;
}
.subtitle {
  text-align: center;
  font-weight: 300;
  font-size: 3vw;
}
.btn-secondary {
  background-color: #feb249;
  border-color: #feb249;
  width: 100%;
  padding: 1vw;
  font-size: 2vw;
  border-radius: 10px;
  margin-top: 5%;
}
.btn-link {
  width: 30%;
}
@media screen and (min-width: 717px) {
  img {
    display: none;
  }
}
@media screen and (max-width: 1150px) {
  .bigContainer {
    margin-top: 30%;
  }
  .title {
    font-size: 5.5vw;
  }
  .subtitle {
    font-size: 3.5vw;
  }
  .btn-secondary {
    font-size: 3vw;
  }
  .btn-link {
    width: 40%;
  }
}
@media screen and (max-width: 716px) {
  img {
    width: 100%;
  }
  .bigContainer {
    padding: 8vw;
    margin-top: 5vh;
  }
  .btn-secondary {
    font-size: 4vw;
    padding: 2vw;
  }
  .subtitle {
    font-size: 4vw;
  }
  .btn-link {
    width:50%;
  }
}
</style>
