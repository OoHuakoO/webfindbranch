<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <b-img src="~assets/BU_logo_horizontal.png" fluld />
      <p class="title">กิจกรรมสื่อวิดีโอเพื่อสร้างแรงบันดาลใจ</p>
      <p class="subtitle">
        โปรดเลือกความสนใจและทักษะที่ต้องการศึกษาเพิ่มเติม <br />
        เพื่อรับชมวิดีโอของสาขาวิชาใน<span class="subtitie-bold"
          >คณะเทคโนโลยีสารสนเทศและนวัตกรรม มหาวิทยาลัยกรุงเทพ </span
        ><br />
        ที่เหมาะกับคุณผ่านแบบสอบถามสั้น ๆ <br />
        “กรุณาทำแบบสอบถามต่อไปนี้เพื่อรับชมสื่อวิดีโอของสาขาวิชาที่เหมาะกับคุณ”
      </p>

      <nuxt-link class="btn-link" to="/selectChoice/page1">
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
  padding: 60px;
  display: flex;
  flex-direction: column;
  background-image: url('~assets/backgroundCom.png');
  background-size: cover;
  background-repeat: no-repeat;
}
.title {
  font-weight: bold;
  font-size: 3vw;
  text-align: center;
}
.subtitle {
  text-align: center;
  font-weight: 300;
  font-size: 2vw;
}
.subtitie-bold {
  font-weight: 700;
}
.btn-secondary {
  background-color: #feb249;
  border-color: #feb249;
  width: 100%;
  padding: 1vw;
  font-size: 1.5vw;
  border-radius: 10px;
  margin-top: 5%;
}
.btn-link {
  width: 25%;
}
img {
  width: 20%;
  margin-bottom: 2%;
}
@media screen and (max-width: 1150px) {
  .bigContainer {
    margin-top: 20%;
    background-image: none;
  }
  img {
    width: 50%;
    margin-bottom: 5%;
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
}
@media screen and (max-width: 716px) {
  .bigContainer {
    padding: 7vw;
    margin-top: 15vh;
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
