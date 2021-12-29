<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <div class="Container">
        <p class="textSeeVideo">ดูวีดีโอสาขาอื่นๆ</p>
        <nuxt-link
          v-for="(item, index) in itemOtherVideo"
          :key="index"
          class="rowVideo"
          :to="`/videoShow/${item.name}`"
        >
          <img :src="item.picture" alt="Image" class="imgSeeOtherVideo" />
          <div class="boxTextVideo">
            <p>{{ item.name }}</p>
          </div>
        </nuxt-link>
      </div>
      <p class="titleJob">สาขาอาชีพที่สามารถนำไปต่อยอดในอนาคต</p>

      <div v-if="branch == 'สาขาวิชาเทคโนโลยีสารสนเทศ'" class="mt-4 boxCard">
        <b-card
          v-for="(item, index) in jobIT"
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
          v-for="(item, index) in jobIT"
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

      <div v-if="branch == 'สาขาวิชาเกมและสื่อเชิงโต้ตอบ'" class="mt-4 boxCard">
        <b-card
          v-for="(item, index) in jobGIM"
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
          v-for="(item, index) in jobGIM"
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

      <div v-if="branch == 'สาขาวิชาวิทยาการคอมพิวเตอร์'" class="mt-4 boxCard">
        <b-card
          v-for="(item, index) in jobCS"
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
          v-for="(item, index) in jobCS"
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

      <div
        v-if="
          branch ==
          'สาขาวิชาวิทยาการคอมพิวเตอร์ มุ่งเน้นความมั่นคงปลอดภัยไซเบอร์และวิทยาการข้อมูล'
        "
        class="mt-4 boxCard"
      >
        <b-card
          v-for="(item, index) in jobDS"
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
          v-for="(item, index) in jobDS"
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
    </div>
      <Footer />
  </div>
</template>

<script>
import Header from '@/components/header'
import Footer from '@/components/footer'
export default {
  components: {
    Header,
  },
  data() {
    return {
      branch: this.$route.params.branch,
      itemOtherVideo: [
        {
          name: 'สาขาวิชาเกมและสื่อเชิงโต้ตอบ',
          picture: require('@/assets/otherGIM.png'),
        },
        {
          name: 'สาขาวิชาวิทยาการคอมพิวเตอร์',
          picture: require('@/assets/otherCS.png'),
        },
        {
          name: 'สาขาวิชาเทคโนโลยีสารสนเทศ',
          picture: require('@/assets/otherIT.png'),
        },
        {
          name: 'สาขาวิชาวิทยาการคอมพิวเตอร์ มุ่งเน้นความมั่นคงปลอดภัยไซเบอร์และวิทยาการข้อมูล',
          picture: require('@/assets/otherDSC.png'),
        },
      ],

      jobIT: [
        {
          titleDetail: 'Programmer / Developer',
          subtitleDetail:
            'อาชีพที่กำลังเป็นที่นิยมที่สุดอาชีพหนึ่งในโลกยุคใหม่ เทคโนโลยีเข้ามามีบทบาทในชีวิตของเราอย่างยิ่ง การวิเคราะห์ออกแบบและพัฒนาซอฟต์แวร์ให้ตรงตามความต้องการการใช้งานและมีความทันสมัยจึงมีความสำคัญ ทักษะการเขียนโปรแกรมเป็นทักษะพิเศษและเฉพาะทางที่องค์กรหรือธุรกิจในโลกยุคดิจิตอล ส่งผลให้รายได้ของสายงานด้านวิศกรรมซอฟต์แวร์และการเขียนโปรแกรมเป็นสายงานที่มีรายได้อยู่ในอันดับแรก ๆ ของโลก หากคุณเป็นคนที่รักการเรียนรู้ตลอดเวลา ชอบทดลองอะไรใหม่ ๆ และมีความคิดเป็นเหตุเป็นผล โปรแกรมเมอร์คือหนึ่งอาชีพที่ตอบโจทย์สำหรับคุณ',
          picture: require('@/assets/programmer.jpg'),
        },
        {
          titleDetail: 'IT Manager',
          subtitleDetail:
            'ธุรกิจในโลกสมัยปัจจุบันล้วนขับเคลื่องด้วยเทคโนโลยี การนำเทคโนโลยีต่าง ๆ เข้ามาประยุกต์ใช้กับองค์กรและธุรกิจดังนั้นจึงเป็นส่วนที่สำคัญในการบริหารจัดการทรัพยากร ไม่ว่าจะเป็นการจัดการเทคโนโลยี บุคลากรที่มีความรู้และงบประมาณในส่วนของเทคโนโลยี เป็นการติดอาวุธให้กับองค์กรเพื่อให้พร้อมดำเนินธุรกิจในโลกยุคดิจิตอลเพื่อให้เกิดการทำงานอย่างมีประสิทธิภาพและสอดคล้องกับยุคสมัย',
          picture: require('@/assets/it_man.png'),
        },
        {
          titleDetail: 'IT Supporter',
          subtitleDetail:
            'ในการทำงานที่และการสร้างสรรค์ผลงานให้เกิดประสิทธิภาพสูง ความพร้อมด้านซอฟต์แวร์และฮาร์ดแวร์ถือเป็นสิ่งที่สำคัญ IT Support คือตำแหน่งงานที่มีหน้าที่ดูแลรับผิดชอบ จัดการ แก้ไข ซ่อมแซม บำรุงรักษาเครื่องใช้อุปกรณ์คอมพิวเตอร์ ตลอดจนซอฟต์แวร์และฮาร์ดแวร์ขององค์กรให้อยู่ในสภาพที่ดี พร้อมใช้งานอยู่ตลอดเวลาเพื่อให้ตอบโจทย์การทำงานที่มีความสำคัญสูงในระดับองค์กรและผลประกอบการของธุรกิจ รวมถึงการป้องกันความผิดพลาดที่อาจจะเกิดขึ้นระหว่างทำงาน',
          picture: require('@/assets/it_support.png'),
        },
        {
          titleDetail: 'Web Front-End Developer',
          subtitleDetail:
            'ผู้ออกแบบ User Experience และ User Interface (UX/UI) ประยุกต์ใช้หลักการออกแบบแก่การพัฒนาเว็บไซต์หรือแฟลตฟอร์มต่างๆ สร้างสรรค์ประสบการณ์การใช้งานแก่ผู้ใช้ เรียนรู้การปฏิสัมพันธ์กับผู้ใช้ นำฟีดแบคมาปรับใช้ เรียนรู้พฤติกรรมศาสตร์ นำเอาหลักการในการแก้ไขปัญหาด้านการใช้งานมาประยุกต์ใช้ในการพัฒนา ออกแบบลักษณะการใช้งาน จุดประสงค์เพื่อดึงดูดความสนใจและความทันสมัย สื่อสารกับอารมณ์ของผู้ใช้งาน นำเอามุมมองและแง่คิดต่างๆ มาสร้างสรรค์ผลงาน',
          picture: require('@/assets/front end.jpg'),
        },
      ],
      jobDS: [
        {
          titleDetail: 'Data Scientist',
          subtitleDetail:
            'ในปัจจุบัน ข้อมูลมีค่ามากกว่าทองคำจึงมีศาสตร์ที่เรียกว่า “วิทยาการข้อมูล” คือการนำข้อมูลที่มหาสารมาทำการรวบรวม จัดการ จัดเก็บ ตรวจสอบ วิเคราะห์ วิจัย และนำเสนอเพื่อประยุกต์นำข้อมูลเหล่านั้นไปใช้งาน ไม่ว่าจะเป็น วิทยาการข้อมูล การเขียนโปรแกรม วิทยาศาสตร์ คณิตศาสตร์ สถิติ ธุรกิจและการตลาด เพื่อที่จะนำเอากระบวนการ อัลกอริทึม มาทำเหมืองข้อมูลและวิเคราะห์ข้อมูลขนาดใหญ่ แก่องค์กรและธุรกิจเพื่อให้เกิดประสิทธิภาพสูงสุด เป็นอีกหนึ่งสายงานที่รายได้สูงและเป็นสายงานเป็นที่ต้องการมากที่สุดในปัจจุบันและอนาคต',
          picture: require('@/assets/Data Science.png'),
        },
        {
          titleDetail: 'Cyber Soldier',
          subtitleDetail:
            'ในยุคดิจิตอลที่มีอินเตอร์เน็ตเป็นศูนย์กลาง ข้อมูลจึงมีความสำคัญอย่างยิ่งกับองค์กรและธุรกิจต่าง ๆ โดยเฉพาะภาครัฐที่ทำหน้าที่ใช้อำนาจตอธิปไตยในการบริหารงานทั้งประเทศ ข้อมูลจึงมีผลต่อความมั่นคงและปลอดภัยของชาติ จึงต้องการบุคลากรที่มีความรู้เฉพาะทาง เพื่อแยกแยะ ปกป้อง ตรวจจับ ตอบสนอง กู้คืนข้อมูลจากภัยคุกคามทางไซเบอร์คล้ายกับการดูแลรักษาความสงบของประเทศเหมือบกับอาชีพทหารและตำรวจ',
          picture: require('@/assets/cyber.png'),
        },
        {
          titleDetail: 'Cyber Security Analyst',
          subtitleDetail:
            'ตำแหน่งงานระดับเริ่มต้นในด้านความปลอดภัยทางไซเบอร์และเป็นตัวเลือกยอดนิยมสำหรับผู้มาใหม่ในสายงาน  โดยเริ่มจากการเข้ารหัสการส่งข้อมูล ทำการประเมินความเสี่ยงสร้างไฟร์วอลล์ ปกป้องข้อมูลที่ละเอียดอ่อน วิเคราะห์ความปลอดภัยทางไซเบอร์',
          picture: require('@/assets/cyberanaly.jpg'),
        },
        {
          titleDetail: 'Data Analyst',
          subtitleDetail:
            'นักวิเคราะห์ข้อมูลคืองานที่นำข้อมูลของลูกค้ามาวิเคราะห์ให้เกิดประโยชน์ เช่น การหาข้อมูลธุรกิจเชิงลึก (ฺBusiness Insight) เพื่อนำไปสนับสนุนการติดสินใจ ต่อยอดในแผนกลยุทธ์ (Strategy) หรือแผนงานต่อ ๆ ไปตามความต้องการของลูกค้า',
          picture: require('@/assets/data_analyst.jpg'),
        },
        {
          titleDetail: 'Cyber Security Specialist',
          subtitleDetail:
            'ผู้เชี่ยวชาญด้านความปลอดภัยทางไซเบอร์ รักษาความปลอดภัยระบบข้อมูลคอมพิวเตอร์ของบริษัท ใช้ทักษะที่มีความเชี่ยวชาญสูงเพื่อป้องกันภัยคุกคามต่อองค์กร เช่นมัลแวร์ ไวรัสฟิชชิ่ง และการโจมตีแบบ Denial-of-service attacks (DDOS)',
          picture: require('@/assets/cyber.png'),
        },
      ],
      jobGIM: [
        {
          titleDetail: 'Game Developer',
          subtitleDetail:
            'ผู้อยู่เบื้องหลังการผลิตเกมออกสู่ตลาด ใช้ความรู้ในการพัฒนาระบบและการเขียนโปรแกรมสร้างสรรค์สื่อที่หลายคนให้คำนิยามว่าเป็นสื่อแห่งโลกอนาคต เนื่องจากอุตสาหกรรมเกมที่มีการเติบโตอย่างมากในโลกยุคดิจิตอล เกมจึงเป็นจุดร่วมของจินตนาการและความรู้ เป็นเครื่องมือที่ช่วยส่งเสริมหลายธุรกิจ รวมถึงเป็นไอคอนและปรัชญาของคนรุ่นใหม่ที่สามารถสร้างสรรค์สิ่งต่างผ่านแนวคิดของการสร้างเกมได้',
          picture: require('@/assets/game-dev.jpg'),
        },
        {
          titleDetail: 'Game Designer',
          subtitleDetail:
            'อาชีพที่เปรียบเสมือนผู้กำกับภาพยนตร์ คิดค้นรูปแบบเกมทั้งหมด อาทิ วิธีการเล่น กฎกติกา ระดับความยาก ระยะเวลาที่ใช้ในการเล่น รวมถึงลักษณะหน้าตาของเกม และตลอดการทำงานจะเป็นผู้ที่มีหน้าที่ควบคุมดูแลภาพรวมของเกมตั้งแต่การออกแบบภาพร่างในขั้นต้น การทำให้เกมมีการเคลื่อนไหวไปจนถึงการเขียนโปรแกรมว่าการพัฒนาเกมมีภาพรวมตรงตามที่ต้องการหรือไม่',
          picture: require('@/assets/game-design.jpg'),
        },
        {
          titleDetail: 'Animator',
          subtitleDetail:
            'อาชีพที่คนรุ่นใหม่กำลังให้ความสนใจ โดยเฉพาะผู้ที่สนใจการออกแบบและสื่อภาพเคลื่อนไหว ทั้ง Animation, Visual Effect หรือ Motion Graphics สามารถนำทักษะไปประยุกต์กับงานสร้างสรรค์หลากหลายรูปแบบ ตั้งแต่การออกแบบภาพเกม และเบื้องหลัง Computer Graphic ของการพัฒนาภาพยนตร์',
          picture: require('@/assets/animator.jpg'),
        },
      ],
      jobCS: [
        {
          titleDetail: 'Programmer / Developer',
          subtitleDetail:
            'อาชีพที่กำลังเป็นที่นิยมที่สุดอาชีพหนึ่งในยุคปัจจุบัน เทคโนโลยีเข้ามามีบทบาทในชีวิตของเราอย่างยิ่ง การวิเคราะห์ออกแบบและพัฒนาซอฟต์แวร์ให้ตรงตามความต้องการการใช้งานและมีความทันสมัยจึงมีความสำคัญ ทักษะการเขียนโปรแกรมเป็นทักษะพิเศษและเฉพาะทางที่องค์กรหรือธุรกิจในโลกยุคดิจิตอล ส่งผลให้รายได้ของสายงานด้านวิศกรรมซอฟต์แวร์และการเขียนโปรแกรมเป็นสายงานที่มีรายได้อยู่ในอันดับแรก ๆ ของโลก หากคุณเป็นคนที่รักการเรียนรู้ตลอดเวลา ชอบทดลองอะไรใหม่ ๆ และมีความคิดเป็นเหตุเป็นผล โปรแกรมเมอร์คือหนึ่งอาชีพที่ตอบโจทย์สำหรับคุณ',
          picture: require('@/assets/programmer.jpg'),
        },
        {
          titleDetail: 'Data Engineer',
          subtitleDetail:
            'ผู้สร้างระบบในการส่งข้อมูล และระบบจัดเก็บข้อมูล เช่น Data Warehouse หรือ Data Lake อาชีพที่เน้นความสามารถด้านการเขียนโปรแกรม Software Engineering และความรู้เกี่ยวกับเครื่องมือการจัดการ Big Data',
          picture: require('@/assets/database_design.jpg'),
        },
        {
          titleDetail: 'Full-Stack Developer',
          subtitleDetail:
            'นักพัฒนาเว็บอย่างเต็มรูปแบบทั้งหน้าบ้านและหลังบ้าน หรือวิศวกรที่ทำงานร่วมกับ Front End และ Back End ของเว็บไซต์หรือแอปพลิเคชัน ผู้จัดการโครงการที่เกี่ยวข้องกับฐานข้อมูลและสร้างเว็บไซต์ที่รองรับผู้ใช้บริการ หรือแม้กระทั่งทำงานกับผู้รับบริการในช่วงการวางแผนสร้างโครงการต่าง ๆ',
          picture: require('@/assets/full stack.jpg'),
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
  margin-bottom: 5%;
}
.textSeeVideo {
  font-size: 2.5vw;
  text-align: center;
}
.rowVideo {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-bottom: 5%;
  text-decoration: none;
  justify-content: center;
}
.imgSeeOtherVideo {
  width: 40%;
  border-radius: 10px;
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
.boxCard {
  width: 75%;
}
.cardResponsiveCom {
  margin-bottom: 3%;
}
.titleJob {
  font-weight: bold;
  font-size: 2.5vw;
  text-align: center;
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
.bigContainer {
  padding: 5vh 1vw 1vh 1vw;
  align-items: center;
  justify-content: center;
  display: flex;
  flex-direction: column;
}
.Container {
  width: 40%;
  margin-left: 5%;
  margin-bottom: 2%;
}
.boxTextVideo {
  justify-content: center;
  align-items: center;
  display: flex;
  width: 60%;
  font-size: 1.5vw;
  margin-left: 5%;
  text-align: center;
  border-left: solid 2px #feb249;
  padding: 4px;
  color: #feb249;
}
.boxImage {
  border-radius: 20px;
  cursor: pointer;
  width: 100%;
}

@media screen and (max-width: 1150px) {
  .titleJob {
    font-size: 4vw;
  }
  .boxCard {
    width: 95%;
  }
  .titleDetail {
    font-size: 2.5vw;
  }
  .subtitleDetail {
    font-size: 1.4vw;
  }
  .bigContainer {
    padding: 3vh 10vw 1vh 10vw;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .Container {
    width: 90%;
    margin-top: 4%;
  }
  .textSeeVideo {
    font-size: 3.5vw;
    margin-bottom: 6%;
    margin-top: 3%;
  }
  .imgSeeOtherVideo {
    width: 45%;
    border-radius: 10px;
  }
  .boxTextVideo {
    font-size: 2.5vw;
    margin-left: 5%;
    padding: 10px;
  }
}
@media screen and (min-width: 717px) {
  .cardResponsiveMobile {
    display: none;
  }
}
@media screen and (max-width: 716px) {
  .btn-secondary {
    font-size: 4vw;
  }
  .cardResponsiveCom {
    display: none;
  }
  .cardResponsiveMobile {
    margin-bottom: 3%;
  }
  .boxCard {
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
  .titleJob {
    margin-bottom: 0%;
    margin-top: 5%;
  }
}
</style>
