<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <p class="title">สาขาอาชีพที่สามารถนำไปต่อยอดในอนาคต</p>
      <div class="mt-4 boxCard">
        <b-card class="card">
          <b-row no-gutters>
            <b-col md="4">
              <b-card-img
                src="https://cdn.dribbble.com/users/206362/screenshots/14453538/media/cfe80febeed64218b34e18f518ca9ae9.jpg?compress=1&resize=400x300"
                alt="Image"
                class="rounded-1"
              ></b-card-img>
            </b-col>
            <b-col md="6">
              <b-card-text class="rightBox">
                <p class="titleDetail">Data Science</p>
                <p class="subtitleDetail">
                  สายงานที่ได้รับความนิยมสูง
                  และขึ้นชื่อว่าเป็นสายงานที่คนต้องการเป็นมากที่สุดในโลก
                  การวิเคราะข้อมูลเป้นศาสตร์ที่มีความสำคัญมากในโลกยุคใหม่
                  การวิเคราะห์ข้อมูลเพื่อให้องค์กรและธุรกิจนำข้อมุลไปใช้ให้เกิดประโยชน์สูงสุด
                </p>
              </b-card-text>
            </b-col>
          </b-row>
        </b-card>

        <b-card class="card">
          <b-row no-gutters>
            <b-col md="4">
              <b-card-img
                src="https://cdn.dribbble.com/users/206362/screenshots/14453538/media/cfe80febeed64218b34e18f518ca9ae9.jpg?compress=1&resize=400x300"
                alt="Image"
                class="rounded-1"
              ></b-card-img>
            </b-col>
            <b-col md="6">
              <b-card-text class="rightBox">
                <p class="titleDetail">Programmer & Developer</p>
                <p class="subtitleDetail">
                  ปัจจุบันภาคธุรกิจมีการเร่งพัฒนาระบบงานต่าง ๆ
                  ไม่ว่าจะเป็นเว็บไซต์
                  และแอปพลิเคชันที่รองรับการใช้งานบนสมาร์ทดีไวซ์ทุกแพลตฟอร์ม
                  เพื่อนำไปสู่การให้บริการและเข้าถึงกลุ่มลูกค้า
                  รวมถึงการขยายตลาดใหม่ ๆ สายงานนี้จึงเป็นส่วนขับเคลื่อนที่สำคัญ
                </p>
              </b-card-text>
            </b-col>
          </b-row>
        </b-card>
      </div>
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
.rightBox {
  padding: 1px;
  margin-left: 5%;
  margin-top: 2%;
}
.card {
  margin-bottom: 3%;
}
.boxCard {
  width: 75%;
}
.bigContainer {
  justify-content: center;
  align-items: center;
  padding: 80px;
  display: flex;
  flex-direction: column;
}
.title {
  font-weight: bold;
  font-size: 40px;
  text-align: center;
  color: #feb249;
}
.subtitle {
  text-align: center;
  font-weight: 300;
  font-size: 30px;
}
.titleDetail {
  font-size: 25px;
  color: #feb249;
}
.subtitleDetail {
  font-size: 16px;
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
