<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <p class="title">คุณสนใจที่จะศึกษาศาสตร์และความรู้เพิ่มเติมด้านใด</p>
      <p class="subtitle">กรุณาเลือก 3 หัวข้อที่คุณสนใจ</p>
      <div class="flexButton">
        <div class="columnButton">
          <div
            v-for="(item, index) in choice.slice(0, 4)"
            class="rowButton"
            :key="index"
          >
            <div
              @click="selectedChoice(index)"
              :class="
                choiceDisable && !choice[index].check
                  ? 'disableRadio'
                  : choice[index].check
                  ? 'activeRadio'
                  : 'nonActiveRadio'
              "
            >
              <div class="smallCircle" v-if="choice[index].check"></div>
            </div>
            <span> {{ item.name }}</span>
          </div>
        </div>
        <div class="columnButton">
          <div
            v-for="(item, index) in choice.slice(4, 9)"
            class="rowButton"
            :key="index"
          >
            <div
              @click="selectedChoice(index + 4)"
              :class="
                choiceDisable && !choice[index + 4].check
                  ? 'disableRadio'
                  : choice[index + 4].check
                  ? 'activeRadio'
                  : 'nonActiveRadio'
              "
            >
              <div class="smallCircle" v-if="choice[index + 4].check"></div>
            </div>
            <span> {{ item.name }}</span>
          </div>
        </div>
      </div>
      <nuxt-link
        v-if="choiceDisable"
        class="btn-link"
        :to="{
          path: pathNavigate,
        }"
      >
        <b-button @click="saveChoice()">ถัดไป</b-button>
      </nuxt-link>
      <div v-if="!choiceDisable" class="boxButtonDisable">
        <b-button class="buttonDisable">ถัดไป</b-button>
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
      pointBranch: {
        pointIT: this.$nuxt._route.query.pointBranch.pointIT,
        pointGIM: this.$nuxt._route.query.pointBranch.pointGIM,
        pointCS: this.$nuxt._route.query.pointBranch.pointCS,
      },
      countPoint: 0,
      choiceDisable: false,
      pathNavigate: '',
      choice: [
        {
          name: 'ธุรกิจ E-Business',
          check: false,
        },
        {
          name: 'ระบบสารสนเทศภายในองค์กร',
          check: false,
        },
        {
          name: 'โมเดล 2D-3D',
          check: false,
        },
        {
          name: 'การสร้างและพัฒนาเกม',
          check: false,
        },
        {
          name: 'ธุรกิจอุตสาหกรรมเกม',
          check: false,
        },
        {
          name: 'พัฒนาแอปพลิเคชัน',
          check: false,
        },
        {
          name: 'AI และการวิเคราะห์ข้อมูล',
          check: false,
        },
        {
          name: 'ระบบความปลอดภัย',
          check: false,
        },
      ],
    }
  },
  mounted() {
    if (
      this.$nuxt._route.query.pointBranch.pointIT === undefined &&
      this.$nuxt._route.query.pointBranch.pointGIM === undefined &&
      this.$nuxt._route.query.pointBranch.pointCS === undefined
    ) {
      this.$router.push({ path: '/selectChoice/page1' })
    }
  },
  methods: {
    async saveChoice() {
      let listChoice = []
      this.choice.map((item) => {
        if (item.check) {
          listChoice.push(item.name)
        }
      })
      await this.$axios
        .post('https://webfindbranchserver.onrender.com/choice', {
          listChoice: listChoice,
        })
        .then((res) => {
          console.log(JSON.stringify(res.data))
        })
    },
    selectedChoice(index) {
      this.choice[index].check = !this.choice[index].check
      if (this.choiceDisable) {
        if (this.choice[index].check) {
          this.choice[index].check = !this.choice[index].check
        }
      }
      if (!this.choice[index].check) {
        this.choiceDisable = false
      }
      this.mapChoice()
    },
    mapChoice() {
      this.countPoint = 0
      this.pointBranch.pointIT = this.$nuxt._route.query.pointBranch.pointIT
      this.pointBranch.pointGIM = this.$nuxt._route.query.pointBranch.pointGIM
      this.pointBranch.pointCS = this.$nuxt._route.query.pointBranch.pointCS
      this.choice.map((item) => {
        if (item.check === true && this.countPoint < 3) {
          this.countPoint++
          if (this.countPoint === 3) {
            this.choiceDisable = true
          }
          if (item.name === 'ธุรกิจ E-Business') {
            this.pointBranch.pointIT = this.pointBranch.pointIT + 1
          } else if (item.name === 'ระบบสารสนเทศภายในองค์กร') {
            this.pointBranch.pointIT = this.pointBranch.pointIT + 1
          } else if (item.name === 'โมเดล 2D-3D') {
            this.pointBranch.pointGIM = this.pointBranch.pointGIM + 1
          } else if (item.name === 'การสร้างและพัฒนาเกม') {
            this.pointBranch.pointGIM = this.pointBranch.pointGIM + 1
          } else if (item.name === 'ธุรกิจอุตสาหกรรมเกม') {
            this.pointBranch.pointGIM = this.pointBranch.pointGIM + 1
          } else if (item.name === 'พัฒนาแอปพลิเคชัน') {
            this.pointBranch.pointIT = this.pointBranch.pointIT + 0.5
            this.pointBranch.pointGIM = this.pointBranch.pointCS + 0.5
          } else if (item.name === 'AI และการวิเคราะห์ข้อมูล') {
            this.pointBranch.pointCS = this.pointBranch.pointCS + 1
          } else if (item.name === 'ระบบความปลอดภัย') {
            this.pointBranch.pointCS = this.pointBranch.pointCS + 1
          }
          if (
            this.pointBranch.pointIT > this.pointBranch.pointGIM &&
            this.pointBranch.pointIT > this.pointBranch.pointCS
          ) {
            this.pathNavigate = '/selectBranch/สาขาวิชาเทคโนโลยีสารสนเทศ'
          } else if (
            this.pointBranch.pointGIM > this.pointBranch.pointIT &&
            this.pointBranch.pointGIM > this.pointBranch.pointCS
          ) {
            this.pathNavigate = '/selectBranch/สาขาวิชาเกมและสื่อเชิงโต้ตอบ'
          } else if (
            this.pointBranch.pointCS > this.pointBranch.pointGIM &&
            this.pointBranch.pointCS > this.pointBranch.pointIT
          ) {
            this.pathNavigate = '/selectChoice/page5'
          } else if (
            this.pointBranch.pointIT === this.pointBranch.pointCS &&
            this.pointBranch.pointGIM === this.pointBranch.pointCS &&
            this.pointBranch.pointIT === this.pointBranch.pointGIM
          ) {
            this.pathNavigate = '/selectChoice/page4'
          } else if (this.pointBranch.pointIT === this.pointBranch.pointGIM) {
            this.pathNavigate = '/selectChoice/page3'
          } else if (
            this.pointBranch.pointIT === this.pointBranch.pointCS ||
            this.pointBranch.pointGIM === this.pointBranch.pointCS
          ) {
            this.pathNavigate = '/selectChoice/page4'
          }
          // console.log('this.pointBranch.pointIT', this.pointBranch.pointIT)
          // console.log('this.pointBranch.pointGIM', this.pointBranch.pointGIM)
          // console.log('this.pointBranch.pointCS', this.pointBranch.pointCS)
        }
      })
    },
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
span {
  margin-left: 10px;
  font-weight: 600;
  font-size: 1.3vw;
}
.bigContainer {
  justify-content: center;
  align-items: center;
  display: flex;
  flex-direction: column;
  padding: 3vw;
  height: 100%;
}
.title {
  font-weight: bold;
  font-size: 2.5vw;
  text-align: center;
}
.subtitle {
  text-align: center;
  font-weight: 300;
  font-size: 2vw;
}
.btn-secondary {
  background-color: #feb249;
  border-color: #feb249;
  width: 100%;
  padding: 1vw;
  font-size: 1.5vw;
  border-radius: 10px;
  margin-top: 1vh;
}
.boxButtonDisable {
  width: 20%;
}
.buttonDisable {
  background-color: #9a9a9c;
  border-color: #9a9a9c;
  width: 100%;
  padding: 1vw;
  font-size: 1.5vw;
  border-radius: 10px;
  margin-top: 1vh;
}
.smallCircle {
  background-color: #ffffff;
  width: 100%;
  height: 100%;
  border-radius: 200px;
}
.activeRadio {
  width: 30px;
  height: 30px;
  background-color: #feb249;
  border-radius: 200px;
  cursor: pointer;
  padding: 7px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.nonActiveRadio {
  width: 30px;
  height: 30px;
  background-color: #ffffff;
  border-radius: 200px;
  border: solid 2px #696880;
  cursor: pointer;
}
.disableRadio {
  width: 30px;
  height: 30px;
  background-color: #d5d5dd;
  border-radius: 200px;
  border: solid 2px #696880;
}
.nonActiveRadio:hover {
  width: 30px;
  height: 30px;
  background-color: #ffffff;
  border-radius: 200px;
  border: solid 2px #feb249;
  cursor: pointer;
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
  width: 60%;
  margin-top: 30px;
}
.btn-link {
  width: 20%;
}
@media screen and (max-width: 1150px) {
  .bigContainer {
    padding: 3vw;
    margin-top: 20vh;
  }
  .title {
    font-size: 5vw;
  }
  .subtitle {
    font-size: 4vw;
  }
  .flexButton {
    width: 70%;
  }
  span {
    margin-left: 10px;
    font-size: 2vw;
  }
  .btn-secondary {
    padding: 1.5vw;
    font-size: 3vw;
  }
  .btn-link {
    width: 40%;
  }
  .boxButtonDisable {
    width: 40%;
  }
  .buttonDisable {
    padding: 1.5vw;
    font-size: 3vw;
  }
}
@media screen and (max-width: 716px) {
  .bigContainer {
    padding: 4vw;
    margin-top: 5vh;
  }
  .flexButton {
    width: 70%;
    margin-top: 15px;
    flex-direction: column;
    margin-left: 20%;
  }
  .title {
    font-size: 7vw;
  }
  .subtitle {
    font-size: 5vw;
  }
  span {
    margin-left: 10px;
    font-size: 3.5vw;
  }
  .nonActiveRadio {
    width: 20px;
    height: 20px;
    border: solid 1px #696880;
  }
  .nonActiveRadio:hover {
    width: 20px;
    height: 20px;
    border: solid 1px #feb249;
  }
  .activeRadio {
    width: 20px;
    height: 20px;
    padding: 5px;
  }
  .disableRadio {
    width: 20px;
    height: 20px;
    padding: 5px;
    border: solid 1px #696880;
  }
  .btn-secondary {
    padding: 2vw;
    font-size: 3vw;
  }
  .btn-link {
    width: 40%;
    margin-bottom: 10%;
  }
  .boxButtonDisable {
    width: 40%;
    margin-bottom: 10%;
  }
  .buttonDisable {
    padding: 2vw;
    font-size: 3vw;
  }
}
@media screen and (max-width: 414px) {
  .flexButton {
    width: 80%;
    margin-top: 20px;
  }
  .activeRadio {
    width: 15px;
    height: 15px;
    padding: 4px;
  }
  .disableRadio {
    width: 15px;
    height: 15px;
    padding: 4px;
  }
  .nonActiveRadio {
    width: 15px;
    height: 15px;
  }
  .nonActiveRadio:hover {
    width: 15px;
    height: 15px;
  }
  .btn-secondary {
    padding: 2vw;
    font-size: 4vw;
  }
  .btn-link {
    width: 50%;
  }
  .boxButtonDisable {
    width: 50%;
  }
  .buttonDisable {
    padding: 2vw;
    font-size: 4vw;
  }
}
</style>
