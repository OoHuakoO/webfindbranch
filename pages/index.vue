<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
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
html,
.body {
  min-height: 100%;
}
.bigContainer {
  justify-content: center;
  align-items: center;
  padding: 100px;
  display: flex;
  flex-direction: column;
}
p {
  font-family: 'Sukhumvit';
}
.title {
  font-weight: bold;
  font-size: 60px;
  text-align: center;
}
.subtitle {
  text-align: center;
  font-weight: 300;
  font-size: 30px;
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
.btn-link {
  width: 30%;
}
</style>
