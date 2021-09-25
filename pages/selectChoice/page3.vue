<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <p class="title">คุณมีความสนใจเฉพาะทางด้านใด</p>
      <p class="subtitle">กรุณาเลือกหัวข้อที่คุณสนใจ</p>
      <div class="boxChoice">
        <div v-for="(item, index) in choice" class="rowButton" :key="index">
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
      <nuxt-link
        v-if="choiceDisable"
        class="btn-link"
        :to="{
          path: pathNavigate,
        }"
      >
        <b-button @click="saveBranch()">ถัดไป</b-button>
      </nuxt-link>
      <div v-if="!choiceDisable" class="boxButtonDisable">
        <b-button class="buttonDisable">ถัดไป</b-button>
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
      countPoint: 0,
      choiceDisable: false,
      pathNavigate: '',
      choice: [
        {
          name: 'การวางระบบ',
          check: false,
        },
        {
          name: 'Storytelling',
          check: false,
        },
      ],
    }
  },
  methods: {
    async saveBranch() {
      this.choice.map(async (item) => {
        if (item.check) {
          if (item.name === 'การวางระบบ') {
            await this.$axios
              .post('https://serverwebfindbranch.herokuapp.com/branch', {
                branchName: 'IT',
              })
              .then((res) => {
                console.log(JSON.stringify(res.data))
              })
          } else if (item.name === 'Storytelling') {
            await this.$axios
              .post('https://serverwebfindbranch.herokuapp.com/branch', {
                branchName: 'GIM',
              })
              .then((res) => {
                console.log(JSON.stringify(res.data))
              })
          }
        }
      })
    },
    async selectedChoice(index) {
      this.choice[index].check = !this.choice[index].check
      if (this.choiceDisable) {
        if (this.choice[index].check) {
          this.choice[index].check = !this.choice[index].check
        }
      }
      if (!this.choice[index].check) {
        this.choiceDisable = false
      }
      if (
        this.choice[index].check &&
        this.choice[index].name === 'การวางระบบ'
      ) {
        this.pathNavigate = '/selectBranch/สาขาวิชาเทคโนโลยีสารสนเทศ'
      } else if (
        this.choice[index].check &&
        this.choice[index].name === 'Storytelling'
      ) {
        this.pathNavigate = '/selectBranch/สาขาวิชาเกมและสื่อเชิงโต้ตอบ'
      }
      this.mapChoice()
    },
    mapChoice() {
      this.countPoint = 0
      this.choice.map((item) => {
        if (item.check === true && this.countPoint < 1) {
          this.countPoint++
          if (this.countPoint === 1) {
            this.choiceDisable = true
          }
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
}
span {
  margin-left: 10px;
  font-weight: 600;
  font-size: 1.5vw;
}
.bigContainer {
  justify-content: center;
  align-items: center;
  display: flex;
  flex-direction: column;
  padding: 5vw;
  height: 100%;
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
.btn-secondary {
  background-color: #feb249;
  border-color: #feb249;
  width: 100%;
  padding: 1vw;
  font-size: 1.8vw;
  border-radius: 10px;
  margin-top: 3vh;
}
.boxButtonDisable {
  width: 30%;
}
.buttonDisable {
  background-color: #9a9a9c;
  border-color: #9a9a9c;
  width: 100%;
  padding: 1vw;
  font-size: 1.8vw;
  border-radius: 10px;
  margin-top: 3vh;
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
.boxChoice {
  margin-bottom: 8%;
  margin-top: 8%;
}
.btn-link {
  width: 30%;
}
@media screen and (max-width: 1150px) {
  .bigContainer {
    padding: 5vw;
    margin-top: 18vh;
  }
  .title {
    font-size: 5vw;
  }
  .subtitle {
    font-size: 4vw;
  }
  span {
    margin-left: 30px;
    font-size: 4vw;
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
  .activeRadio {
    width: 45px;
    height: 45px;
    padding: 10px;
  }
  .nonActiveRadio {
    width: 45px;
    height: 45px;
  }
  .disableRadio {
    width: 45px;
    height: 45px;
  }
  .nonActiveRadio:hover {
    width: 45px;
    height: 45px;
  }
}
@media screen and (max-width: 716px) {
  .bigContainer {
    padding: 4vw;
    margin-top: 15vh;
  }
  .title {
    font-size: 5vw;
  }
  .subtitle {
    font-size: 4vw;
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
  .bigContainer {
    margin-top: 20vh;
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
