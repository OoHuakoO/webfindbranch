<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <p class="title">โปรดเลือกความสนใจของคุณ</p>
      <p class="subtitle">สามารถเลือกมากกว่าหนึ่งหัวข้อ</p>
      <div class="flexButton">
        <div class="columnButton">
          <div
            v-for="(item, index) in choice.slice(0, 5)"
            class="rowButton"
            :key="index"
          >
            <div
              @click="selectedChoice(index)"
              :class="choice[index].check ? 'activeRadio' : 'nonActiveRadio'"
            >
              <div class="smallCircle" v-if="choice[index].check"></div>
            </div>
            <span> {{ item.name }}</span>
          </div>
        </div>
        <div class="columnButton">
          <div
            v-for="(item, index) in choice.slice(5, 10)"
            class="rowButton"
            :key="index"
          >
            <div
              @click="selectedChoice(index + 5)"
              :class="
                choice[index + 5].check ? 'activeRadio' : 'nonActiveRadio'
              "
            >
              <div class="smallCircle" v-if="choice[index + 5].check"></div>
            </div>
            <span> {{ item.name }}</span>
          </div>
        </div>
      </div>
      <p class="note">หมายเหตุ : หลังจากนี้คุณยังคงสามารถแก้ไขความสนใจ</p>
      <nuxt-link class="btn-link" to="/selectBranch/สาขาวิชาเกมและสื่อเชิงโต้ตอบ">
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
  data() {
    return {
      choice: [
        {
          name: 'เล่นวิดีโอเกม',
          check: false,
        },
        {
          name: 'ศิลปะกับการวาดรูป',
          check: false,
        },
        {
          name: 'คณิตศาสตร์และการคำนวณ',
          check: false,
        },
        {
          name: 'การเขียนโปรแกรม',
          check: false,
        },
        {
          name: 'การใช้ซอฟต์แวร์',
          check: false,
        },
        {
          name: 'E - Sport',
          check: false,
        },
        {
          name: 'ระบบอินเทอร์เน็ต',
          check: false,
        },
        {
          name: 'ธุรกิจคอมพิวเตอร์',
          check: false,
        },
        {
          name: 'ออกแบบกราฟิก',
          check: false,
        },
        {
          name: 'แอนิเมชัน',
          check: false,
        },
      ],
    }
  },
  methods: {
    selectedChoice(index) {
      this.choice[index].check = !this.choice[index].check
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
.note {
  margin-top: 30px;
  font-size: 1.5vw;
  font-weight: 300;
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
  width: 50%;
  margin-top: 30px;
}
.btn-link {
  width: 30%;
}
@media screen and (max-width: 1150px) {
  .bigContainer {
    padding: 5vw;
    margin-top: 10vh;
  }
  .title {
    font-size: 5vw;
  }
  .subtitle {
    font-size: 4vw;
  }
  .flexButton {
    width: 60%;
  }
  span {
    margin-left: 10px;
    font-size: 2vw;
  }
  .note {
    margin-top: 30px;
    font-size: 2.5vw;
  }
  .btn-secondary {
    padding: 1.5vw;
    font-size: 3vw;
  }
  .btn-link {
    width: 40%;
  }
}
@media screen and (max-width: 716px) {
  .bigContainer {
    padding: 4vw;
    margin-top: 12vh;
  }
  .flexButton {
    width: 70%;
    margin-top: 15px;
  }
  .title {
    font-size: 7vw;
  }
  .subtitle {
    font-size: 5vw;
  }
  span {
    margin-left: 10px;
    font-size: 3vw;
  }
  .note {
    margin-top: 15px;
    font-size: 3vw;
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
  .btn-secondary {
    padding: 2vw;
    font-size: 3vw;
  }
  .btn-link {
    width: 40%;
  }
}
@media screen and (max-width: 414px) {
  .flexButton {
    width: 80%;
    margin-top: 20px;
  }
  .activeRadio {
    padding: 4px;
  }
  .activeRadio {
    width: 15px;
    height: 15px;
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
  .note {
    margin-top: 15px;
    font-size: 3.2vw;
  }
}
</style>
