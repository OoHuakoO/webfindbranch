<template>
  <div class="body">
    <Header />

    <div class="bigContainer">
      <b-img src="~assets/banner.svg" fluld />
      <p class="title">กิจกรรมสื่อวีดีโอเพื่อสร้างแรง บรรดาลใจ</p>
      <p class="subtitle">
        โปรดเลือกสิ่งที่คุณสนใจ มีทักษะ หรือชื่นชอบ <br />
        เพื่อรับชมวิดีโอของสาขาวิชาที่เหมาะกับคุณ ผ่านแบบสอบถามสั้น ๆ <br />
        ต่อไปนี้เพื่อรับชมสื่อวีดีโอแต่ละสาขา
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
  padding: 90px;
  display: flex;
  flex-direction: column;
  background-image: url('~assets/backgroundCom.png');
  background-size: cover;
  background-repeat: no-repeat;
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
@media screen and (min-width: 1151px) {
  img {
    display: none;
  }
}
@media screen and (max-width: 1150px) {
  .bigContainer {
    margin-top: 8%;
    background-image: none;
  }
  .title {
    font-size: 4.5vw;
  }
  .subtitle {
    font-size: 2.8vw;
  }
  .btn-secondary {
    font-size: 3vw;
  }
  .btn-link {
    width: 40%;
  }
  img {
    width: 100%;
  }
}
@media screen and (max-width: 716px) {
  .bigContainer {
    padding: 7vw;
    margin-top: 6vh;
  }
  .btn-secondary {
    font-size: 4vw;
    padding: 2vw;
  }
  .subtitle {
    font-size: 4vw;
  }
  .btn-link {
    width: 50%;
  }
}
</style>
