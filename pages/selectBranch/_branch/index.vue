<template>
  <div class="body">
    <Header />
    <p class="seeVideo">รับชมวิดีโอในอีก {{ count }}</p>
    <b-progress
      :value="value"
      variant="warning"
      striped
      animated
      class="mt-2 progressbar"
    ></b-progress>
    <div class="bigContainer">
      <p class="title">{{ branch }}</p>
      <p class="subtitle">คือสาขาวิชาที่เหมาะกับคุณ</p>
      <img :src="picture" alt="Image" class="rightImg" />
      <p class="moreText">
        รับชมวิดีโอเพื่อทำความรู้จักกับสิ่งที่น่าสนใจของสาขาวิชาได้เลย !
      </p>
      <nuxt-link
        class="btn-link"
        :to="{
          path: `/videoShow/${branch}`,
        }"
      >
        <b-button>รับชมวีดีโอ</b-button>
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
      picture: '',
      branch: '',
      value: 0,
      max: 100,
      count: 8,
    }
  },
  mounted() {
    this.checkID()
    this.startTimer()
  },
  watch: {
    count: {
      handler: function (val) {
        if (val === 1) {
          this.$router.push({
            path: `/videoShow/${this.branch}`,
          })
        }
      },
    },
  },
  methods: {
    naviagate() {
      $router.push({
        path: `/videoShow/${vm.branch}`,
      })
    },
    checkID() {
      if (this.$route.params.branch === 'สาขาวิชาเทคโนโลยีสารสนเทศ') {
        ;(this.picture = require('@/assets/it.png')),
          (this.branch = 'สาขาวิชาเทคโนโลยีสารสนเทศ')
      } else if (
        this.$route.params.branch ===
        'สาขาวิชาวิทยาการคอมพิวเตอร์ มุ่งเน้นความมั่นคงปลอดภัยไซเบอร์และวิทยาการข้อมูล'
      ) {
        ;(this.picture = require('@/assets/dsc.png')),
          (this.branch =
            'สาขาวิชาวิทยาการคอมพิวเตอร์ มุ่งเน้นความมั่นคงปลอดภัยไซเบอร์และวิทยาการข้อมูล')
      } else if (this.$route.params.branch === 'สาขาวิชาเกมและสื่อเชิงโต้ตอบ') {
        ;(this.picture = require('@/assets/gim.png')),
          (this.branch = 'สาขาวิชาเกมและสื่อเชิงโต้ตอบ')
      } else if (
        this.$route.params.branch === 'สาขาวิชาวิทยาการคอมพิวเตอร์'
      ) {
        ;(this.picture = require('@/assets/cs.png')),
          (this.branch = 'สาขาวิชาวิทยาการคอมพิวเตอร์')
      }
    },
    startTimer() {
      let vm = this
      let timer = setInterval(function () {
        vm.value += 2
        if (vm.value === 20) {
          vm.count = 7
        } else if (vm.value === 36) {
          vm.count = 6
        } else if (vm.value === 54) {
          vm.count = 5
        } else if (vm.value === 68) {
          vm.count = 4
        } else if (vm.value === 80) {
          vm.count = 3
        } else if (vm.value === 98) {
          vm.count = 2
        } else if (vm.value >= 110) {
          vm.count = 1
          clearInterval(timer)
        }
      }, 100)
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
.bigContainer {
  justify-content: center;
  align-items: center;
  padding: 30px;
  display: flex;
  flex-direction: column;
}
.progressbar {
  height: 15px;
}
.seeVideo {
  margin-top: 1%;
  margin-left: 3%;
  font-size: 1.2vw;
}
.title {
  font-weight: bold;
  font-size: 2vw;
  text-align: center;
  color: #feb249;
}
.subtitle {
  text-align: center;
  font-weight: 300;
  font-size: 2vw;
}
.moreText {
  text-align: center;
  font-weight: 300;
  font-size: 1.5vw;
  margin-top: 0%;
}
.btn-secondary {
  background-color: #feb249;
  border-color: #feb249;
  width: 100%;
  padding: 1vw;
  font-size: 2vw;
  border-radius: 10px;
  margin-top: 5%;
}
.btn-link {
  width: 25%;
  margin-bottom: 5%;
}
.rightImg {
  width: 20%;
  margin-top: 0%;
  margin-bottom: 2%;
}
@media screen and (max-width: 1150px) {
  .moreText {
    font-size: 3vw;
    margin-top: 3%;
  }
  .btn-secondary {
    font-size: 3vw;
    margin-top: 5%;
  }
  .btn-link {
    width: 30%;
  }
  .seeVideo {
    font-size: 4vw;
    margin-top: 2%;
  }
  .bigContainer {
    margin-top: 10%;
  }
  .progressbar {
    height: 45px;
  }
  .title {
    font-size: 5vw;
  }
  .subtitle {
    font-size: 4vw;
  }
  .rightImg {
    width: 45%;
    margin-top: 2%;
    margin-bottom: 2%;
  }
}
@media screen and (max-width: 716px) {
  .progressbar {
    height: 30px;
  }
  .bigContainer {
    margin-top: 5%;
  }
  .btn-link {
    width: 35%;
  }
  .seeVideo {
    margin-top: 3%;
  }
}
@media screen and (max-width: 414px) {
  .progressbar {
    height: 30px;
  }
  .bigContainer {
    margin-top: 5%;
  }
  .btn-secondary {
    padding: 2vw;
    font-size: 4vw;
    border-radius: 10px;
    margin-top: 5%;
  }
  .moreText {
    font-size: 3.5vw;
  }
  .btn-link {
    width: 45%;
  }
  .seeVideo {
    margin-top: 5%;
  }
}
</style>
