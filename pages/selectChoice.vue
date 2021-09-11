<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <p class="title">โปรดเลือกความสนใจของคุณ</p>
      <p class="subtitle">สามารถเลือกมากกว่าหนึ่งหัวข้อ</p>
      <div class="flexButton">
        <div class="columnButton">
          <div class="rowButton">
            <div class="radioButton"></div>
            <span>เล่นวิดีโอเกม</span>
          </div>
          <div class="rowButton">
            <div class="radioButton"></div>
            <span>ศิลปะกับการวาดรูป</span>
          </div>
          <div class="rowButton">
            <div class="radioButton"></div>
            <span>คณิตศาสตร์และการคำนวณ</span>
          </div>
          <div class="rowButton">
            <div class="radioButton"></div>
            <span>การเขียนโปรแกรม</span>
          </div>
          <div class="rowButton">
            <div class="radioButton"></div>
            <span>การใช้ซอฟต์แวร์</span>
          </div>
        </div>
        <div class="columnButton">
          <div class="rowButton">
            <div class="radioButton"></div>
            <span>E - Sport</span>
          </div>
          <div class="rowButton">
            <div class="radioButton"></div>
            <span>ระบบอินเทอร์เน็ต</span>
          </div>
          <div class="rowButton">
            <div class="radioButton"></div>
            <span>ธุรกิจคอมพิวเตอร์</span>
          </div>
          <div class="rowButton">
            <div class="radioButton"></div>
            <span>ออกแบบกราฟิก </span>
          </div>
          <div class="rowButton">
            <div class="radioButton"></div>
            <span>แอนิเมชัน</span>
          </div>
        </div>
      </div>
      <p class="note">หมายเหตุ : หลังจากนี้คุณยังคงสามารถแก้ไขความสนใจ</p>
      <nuxt-link class="btn-link" to="/videoShow/สาขาวิชาเกมและสื่อเชิงโต้ตอบ">
        <b-button>ดูสาขาที่เหมาะกับคุณ !</b-button>
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
span {
  margin-left: 10px;
  font-weight: 600;
  font-size: 20px;
}
.bigContainer {
  justify-content: center;
  align-items: center;
  display: flex;
  flex-direction: column;
  padding: 60px;
  height: 100%;
}
.title {
  font-weight: bold;
  font-size: 40px;
  text-align: center;
}
.subtitle {
  text-align: center;
  font-weight: 300;
  font-size: 25px;
}
.note {
  margin-top: 30px;
  font-size: 20px;
  font-weight: 300;
}
.btn-secondary {
  background-color: #feb249;
  border-color: #feb249;
  width: 100%;
  padding: 20px;
  font-family: 'Sukhumvit';
  font-size: 25px;
  border-radius: 10px;
  margin-top: 40px;
}
.radioButton {
  width: 25px;
  height: 25px;
  background-color: #feb249;
  border-radius: 20px;
}
.rowButton {
  flex-direction: row;
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}
.columnButton {
  display: flex;
  flex-direction: column;
}
.flexButton {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 50%;
  margin-top: 30px;
}
.btn-link {
  width: 30%;
}
</style>
