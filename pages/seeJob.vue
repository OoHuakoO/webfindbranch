<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <p class="title">สาขาอาชีพที่สามารถนำไปต่อยอดในอนาคต</p>
      <div class="mt-4 boxCard">
        <b-card v-for="(item, index) in job" :key="index" class="card">
          <b-row no-gutters>
            <b-col md="4">
              <b-card-img
                :src="item.picture"
                alt="Image"
                class="rounded-1"
              ></b-card-img>
            </b-col>
            <b-col md="8">
              <b-card-text class="rightBox">
                <p class="titleDetail">{{ item.titleDetail }}</p>
                <p class="subtitleDetail">
                  {{ item.subtitleDetail }}
                </p>
              </b-card-text>
            </b-col>
          </b-row>
        </b-card>
      </div>
      <nuxt-link class="btn-link" to="/selectChoice">
        <b-button>แก้ไขความสนใจ</b-button>
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
  data() {
    return {
      job: [
        {
          titleDetail: 'Data Science',
          subtitleDetail:
            'สายงานที่ได้รับความนิยมสูงและขึ้นชื่อว่าเป็นสายงานที่คนต้องการเป็นมากที่สุดในโลกการวิเคราะข้อมูลเป้นศาสตร์ที่มีความสำคัญมากในโลกยุคใหม่การวิเคราะห์ข้อมูลเพื่อให้องค์กรและธุรกิจนำข้อมุลไปใช้ให้เกิดประโยชน์สูงสุด',
          picture:
            'https://cdn.dribbble.com/users/206362/screenshots/14453538/media/cfe80febeed64218b34e18f518ca9ae9.jpg?compress=1&resize=400x300',
        },
        {
          titleDetail: 'Programmer & Developer',
          subtitleDetail:
            'ปัจจุบันภาคธุรกิจมีการเร่งพัฒนาระบบงานต่าง ๆ ไม่ว่าจะเป็นเว็บไซต์ และแอปพลิเคชันที่รองรับการใช้งานบนสมาร์ทดีไวซ์ทุกแพลตฟอร์ม เพื่อนำไปสู่การให้บริการและเข้าถึงกลุ่มลูกค้า รวมถึงการขยายตลาดใหม่ ๆ  สายงานนี้จึงเป็นส่วนขับเคลื่อนที่สำคัญ',
          picture:
            'https://cdn.dribbble.com/users/206362/screenshots/14453538/media/cfe80febeed64218b34e18f518ca9ae9.jpg?compress=1&resize=400x300',
        },
        {
          titleDetail: 'Cyper Security',
          subtitleDetail:
            'สำหรับ Cyber Security เป็นอีกหนึ่งสายงานที่สำคัญและเป็นที่ต้องการสูงมากในยุคดิจิทัล เนื่องจากการเติบโตของจำนวนผู้ใช้งานในโลกอินเทอร์เน็ตมีจำนวนเพิ่มสูงขึ้นเรื่อย ๆ ทำให้ต้องมีการสร้างความมั่นใจในระบบต่าง ๆ ว่ามีความปลอดภัยและมีความเป็นส่วนตัวในการเข้าใช้งาน ไม่มีช่องโหว่ที่ก่อให้เกิดอันตรายต่อระบบการทำงานขององค์กร นอกจากนี้ยังรวมถึงด้านกฎหมายที่ Cyber Security จะต้องมีหน้าที่ในการดูแลด้วย เพื่อให้เป็นไปตามมาตรฐาน',
          picture:
            'https://cdn.dribbble.com/users/206362/screenshots/14453538/media/cfe80febeed64218b34e18f518ca9ae9.jpg?compress=1&resize=400x300',
        },
        {
          titleDetail: 'IT Management',
          subtitleDetail:
            'การนำเทคโนโลยีมาประยุกต์ใช้และเสริมความแข็งแกร่งให้กับกระบวนการทางธุรกิจยังมีเพิ่มขึ้นอย่างต่อเนื่อง โดยนำเทคโนโลยีมาเพิ่มศักยภาพให้มีความเป็นอัติโนมัติยิ่งขึ้น ตลาดออฟไลน์มีการหันมาทำออนไลน์มากขึ้น ทำให้เกิดโจทย์ทางธุรกิจใหม่ ๆ ซึ่งต้องการกลุ่มสายงานลูกผสมที่มีความรู้ทางด้านธุรกิจควบคู่กับไอทีมาช่วยพัฒนาซอฟต์แวร์และระบบต่าง ๆ ในเชิงงานโครงการ จึงไม่น่าแปลกใจที่สายงานนี้ติดอันดับ',
          picture:
            'https://cdn.dribbble.com/users/206362/screenshots/14453538/media/cfe80febeed64218b34e18f518ca9ae9.jpg?compress=1&resize=400x300',
        },
        {
          titleDetail: 'Database',
          subtitleDetail:
            'ระบบฐานข้อมูลถือเป็นหัวใจสำคัญในการรองรับและสนับสนุนการพัฒนาต่าง ๆ ส่งผลให้ระบบฐานข้อมูลมีความจำเป็นต้องมีบุคลากรผู้เชี่ยวชาญเข้ามาดูแล ทำให้ตำแหน่ง Database Administrator ยังเป็นที่ต้องการของตลาดอยู่เสมอ',
          picture:
            'https://cdn.dribbble.com/users/206362/screenshots/14453538/media/cfe80febeed64218b34e18f518ca9ae9.jpg?compress=1&resize=400x300',
        },
      ],
    }
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
  padding: 1vw;
  width: 100%;
  height: 100%;
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
  padding: 6vw;
  display: flex;
  flex-direction: column;
}
.title {
  font-weight: bold;
  font-size: 3vw;
  text-align: center;
  color: #feb249;
}
.titleDetail {
  font-size: 1.5vw;
  color: #feb249;
  font-weight: 500;
}
.subtitleDetail {
  font-size: 1vw;
}
.btn-secondary {
  background-color: #feb249;
  border-color: #feb249;
  width: 100%;
  padding: 1vw;
  font-family: 'Sukhumvit';
  font-size: 1.8vw;
  border-radius: 10px;
  margin-top: 40px;
}
.btn-link {
  width: 30%;
}
</style>
