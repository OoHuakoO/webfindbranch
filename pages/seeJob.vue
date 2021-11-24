<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <p class="title">สาขาอาชีพที่สามารถนำไปต่อยอดในอนาคต</p>
      <div class="mt-4 boxCard">
        <b-card
          v-for="(item, index) in job"
          :key="index"
          class="cardResponsiveCom"
        >
          <b-row v-if="(index + 1) % 2 != 0" no-gutters>
            <b-col md="4">
              <b-card-img
                :src="item.picture"
                alt="Image"
                class="rounded-1"
              ></b-card-img>
            </b-col>
            <b-col md="8">
              <b-card-text class="rightBox">
                <span class="titleDetail">{{ item.titleDetail }}</span>
                <p class="subtitleDetail">
                  {{ item.subtitleDetail }}
                </p>
              </b-card-text>
            </b-col>
          </b-row>

          <b-row v-if="(index + 1) % 2 == 0" no-gutters>
            <b-col md="8">
              <b-card-text class="leftBox">
                <span class="titleDetail">{{ item.titleDetail }}</span>
                <p class="subtitleDetail">
                  {{ item.subtitleDetail }}
                </p>
              </b-card-text>
            </b-col>
            <b-col md="4">
              <b-card-img
                :src="item.picture"
                alt="Image"
                class="rounded-1"
              ></b-card-img>
            </b-col>
          </b-row>
        </b-card>

        <b-card
          v-for="(item, index) in job"
          :key="index"
          class="cardResponsiveMobile"
        >
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
                <span class="titleDetail">{{ item.titleDetail }}</span>
                <p class="subtitleDetail">
                  {{ item.subtitleDetail }}
                </p>
              </b-card-text>
            </b-col>
          </b-row>
        </b-card>
      </div>
      <div class="buttomContainer">
        <p class="formText">ขอบคุณสำหรับการเข้าร่วมกิจกรรม</p>
        <hr class="line" />
        <p class="subtitleFormText">กรุณาทำแบบสอบถามหลังหลังเข้าร่วมกิจกรรม</p>
        <a class="subtitleFormText" href="https://forms.gle/MykTAttwrmsTw1FK6"
          >คลิกที่นี่เพื่อทำแบบสอบถาม</a
        >
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
  data() {
    return {
      job: [
        {
          titleDetail: 'Programmer',
          subtitleDetail:
            'หน้าที่ของนักเขียนโปรแกรมหรือนักพัฒนาซอฟต์แวร์คือการเขียนโปรแกรมคอมพิวเตอร์ในการสั่งการให้คอมพิวเตอร์เป็นไปตามที่ต้องการ และอาชีพนี้เป็นที่ต้องการสูงของตลาดแรงงาน ไม่ว่าจะในไทยหรือต่างประเทศ เนื่องด้วยธุรกิจที่เกี่ยวข้องกับไอทีและดิจิทัลมีแนวโน้มเพิ่มสูงขึ้นเรื่อย ๆ',
          picture: require('@/assets/programmer.png'),
        },
        {
          titleDetail: 'Database Designer',
          subtitleDetail:
            'ระบบฐานข้อมูลคือหัวใจสำคัญของการขับเคลื่อนองค์กร ดังนั้นจึงมีความจำเป็นที่จะต้องมีบุคลากรผู้เชี่ยวชาญเข้ามาดูแล ตำแหน่ง database administrator จึงเป็นที่ต้องการของตลาดอยู่เสมอ',
          picture: require('@/assets/database_design.jpg'),
        },
        {
          titleDetail: 'Data Analyst',
          subtitleDetail:
            'การทำงานของนักวิเคราะห์ข้อมูลจะเน้นการใช้ฐานข้อมูลเดิมของผู้บริโภคหรือ big data ในการวิเคราะห์และทำความเข้าใจถึงความต้องการของผู้บริโภค เริ่มจากการตีความโจทย์ธุรกิจ เก็บรวบรวมข้อมูลพื้นฐาน เลือกใช้เครื่องมือในการวิเคราะห์ จัดทำรายงานเพื่ออัปเดตข้อมูลของลูกค้าเพื่อนำไปใช้งานในฝ่ายอื่น',
          picture: require('@/assets/data_analyst.jpg'),
        },
        {
          titleDetail: 'Cyber Security',
          subtitleDetail:
            'สายงานที่สำคัญและเป็นที่ต้องการสูงมากในยุคดิจิตอล ผู้รักษาความปลอดภัยของระบบและปิดช่องโหว่ที่ก่อให้เกิดอันตรายต่อระบบการทำงานขององค์กร',
          picture: require('@/assets/cyber.png'),
        },
        {
          titleDetail: 'Game Developer',
          subtitleDetail:
            'ผู้พัฒนาวิดีโอเกมและสื่อเชิงโต้ตอบ ในอุตสาหกรรมเกมซึ่งเติบโตอย่างมากในปัจจุบันและอนาคต เพิ่มโอกาสทางธุรกิจและนำความรู้ไปต่อยอดในการสร้างสรรค์สื่อรูปแบบให้มีความน่าสนใจยิ่งขึ้น',
          picture: require('@/assets/game-dev.jpg'),
        },
        {
          titleDetail: 'Game Designer',
          subtitleDetail:
            'ผู้ออกแบบรูปแบบวิดีโอเกม ไม่ว่าจะเป็นวิธีการเล่น กฎกติกา ความยากง่าย ระยะเวลาที่ใช้ในการเล่น รวมถึงลักษณะหน้าตาของวิดีโอเกม',
          picture: require('@/assets/game-design.jpg'),
        },
        {
          titleDetail: 'Animator',
          subtitleDetail:
            'อาชีพที่คนรุ่นใหม่กำลังให้ความสนใจ โดยเฉพาะผู้ที่สนใจการออกแบบและสื่อภาพเคลื่อนไหว ไม่ว่าจะเป็น animation, visual effect และ motion graphics',
          picture: require('@/assets/animator.jpg'),
        },
        {
          titleDetail: 'IT Manager',
          subtitleDetail:
            'สายงานลูกผสมที่มีความรู้ทางด้านธุรกิจควบคู่กับไอทีในการพัฒนาซอฟต์แวร์และระบบต่าง ๆ ในเชิงงานโครงการ เสริมสร้างความมั่นคงและศักยภาพแก่กระบวนการทางธุรกิจ อีกทั้งเป็นสายงานติดอันดับความต้องการมากที่สุด',
          picture: require('@/assets/it_man.png'),
        },
        {
          titleDetail: 'IT Supporter',
          subtitleDetail:
            'ผู้รับผิดชอบการจัดการ แก้ไข ซ่อมแซม บำรุงรักษาเครื่องใช้อุปกรณ์คอมพิวเตอร์ ตลอดจนซอฟต์แวร์และฮาร์ดแวร์ขององค์กรให้อยู่ในสภาพดีอยู่เสมอและพร้อมใช้งานตลอดเวลา',
          picture: require('@/assets/it_support.png'),
        },
        {
          titleDetail: 'Network Administrator',
          subtitleDetail:
            'การตรวจสอบ ดูแล และบริหารระบบเครือข่ายคอมพิวเตอร์ขององค์กร การติดตั้งระบบเครือข่าย การควบคุมสิทธิ์ของผู้ใช้งานการป้องกันการบุกรุกเครือข่ายเพื่อรักษาความน่าเชื่อถือของระบบไว้ให้มากที่สุด',
          picture: require('@/assets/network_admin.png'),
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
hr.line {
  border: 1px solid #c5c6d0;
  border-radius: 1px;
}
.body {
  min-height: 100%;
}
.rightBox {
  padding: 1vw;
  width: 100%;
  height: 100%;
  margin-left: 2%;
}
.leftBox {
  padding: 1vw;
  width: 100%;
  height: 100%;
}
.cardResponsiveCom {
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
  margin-top: 2%;
}
.btn-secondary {
  background-color: #feb249;
  border-color: #feb249;
  width: 100%;
  padding: 1vw;
  font-size: 1.8vw;
  border-radius: 10px;
  margin-top: 40px;
}
.btn-link {
  width: 30%;
}
.formText {
  font-size: 2vw;
  color: 'black';
  font-weight: 500;
}
.subtitleFormText {
  font-size: 1vw;
  color: 'black';
}
.buttomContainer {
  width: 75%;
  margin-top: 2%;
}
@media screen and (max-width: 1150px) {
  .title {
    font-size: 4vw;
  }
  .boxCard {
    width: 95%;
  }
  .formText {
    font-size: 2.5vw;
    color: 'black';
    font-weight: 500;
  }
  .subtitleFormText {
    font-size: 1.5vw;
    color: 'black';
  }
  .buttomContainer {
    width: 95%;
  }
  .titleDetail {
    font-size: 2.5vw;
  }
  .subtitleDetail {
    font-size: 1.4vw;
  }
  .btn-secondary {
    padding: 1.5vw;
    font-size: 3vw;
  }
  .btn-link {
    width: 40%;
  }
}
@media screen and (min-width: 717px) {
  .cardResponsiveMobile {
    display: none;
  }
}
@media screen and (max-width: 716px) {
  .cardResponsiveCom {
    display: none;
  }
  .cardResponsiveMobile {
    margin-bottom: 3%;
  }
  .boxCard {
    width: 80%;
  }
  .formText {
    font-size: 3.5vw;
    color: 'black';
    font-weight: 500;
    margin-bottom: 0px;
  }
  .subtitleFormText {
    font-size: 2.5vw;
    color: 'black';
    margin-bottom: 0px;
  }
  .buttomContainer {
    width: 80%;
  }
  .titleDetail {
    font-size: 4vw;
  }
  .subtitleDetail {
    font-size: 3vw;
  }
  .rightBox {
    padding: 0px;
    margin-top: 5%;
  }
  .btn-secondary {
    padding: 1.5vw;
    font-size: 4vw;
    margin-top: 16px;
  }
  .title {
    margin-bottom: 0%;
    margin-top: 5%;
  }
}
</style>
