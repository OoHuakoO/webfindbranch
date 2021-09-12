<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <video class="video" controls="controls" @ended="endedVideo">
        <source :src="require('@/assets/testVideo.mp4')" type="video/mp4" />
      </video>
      <nuxt-link
        v-if="endedVideoState"
        class="btn-link-branch"
        to="/showOtherVideo"
      >
        <b-button>ดูอาชีพเกี่ยวกับสาขา</b-button>
      </nuxt-link>
      <div class="container">
        <p>สาขาวิชาเกมและสื่อเชิงโต้ตอบ</p>
        <p class="yellowText">คือสาขาวิชาที่เหมาะกับคุณ</p>
        <div>
          <p class="textPromote">
            รับชมวิดีโอเพื่อทำความรู้จักกับ สิ่งที่น่าสนใจของสาขาวิชาได้เลย !
          </p>
        </div>
      </div>
    </div>
    <div class="underContainer">
      <nuxt-link class="btn-link" to="/selectChoice">
        <b-button>แก้ไขความสนใจ</b-button>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
import Header from '@/components/header'
import VideoPlayer from 'nuxt-video-player'
require('nuxt-video-player/src/assets/css/main.css')
export default {
  components: {
    Header,
    VideoPlayer,
  },
  data() {
    return {
      endedVideoState: false,
    }
  },
  methods: {
    endedVideo() {
      this.endedVideoState = true
    },
  },
}
</script>
<style scoped>
html,
.body {
  min-height: 100%;
}
* {
  font-family: 'Sukhumvit';
}
p {
  font-weight: bold;
  font-size: 1.8vw;
}
.video {
  width: 60%;
}
.yellowText {
  color: #feb249;
}
.textPromote {
  text-align: center;
}
.underContainer {
  width: 25%;
  margin-bottom: 4%;
  margin-left: 7%;
}
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 50%;
  align-items: center;
  margin-top: 5%;
}
.bigContainer {
  justify-content: center;
  align-items: center;
  padding: 5vw;
  display: flex;
  flex-direction: column;
}
.btn-secondary {
  background-color: #feb249;
  border-color: #feb249;
  width: 100%;
  padding: 1vw;
  font-size: 1.8vw;
  border-radius: 10px;
}
.btn-link {
  width: 100%;
}
.btn-link-branch {
  width: 30%;
  margin-top: 5%;
}
@media screen and (max-width: 1150px) {
  .bigContainer {
    padding: 0vw;
    margin-top: 12vh;
  }
  .btn-secondary {
    padding: 1.5vw;
    font-size: 3vw;
  }
  .video {
    width: 80%;
  }
  p {
    font-size: 3vw;
  }
  .container {
    width: 70%;
    margin-top: 5%;
  }
  .underContainer {
    width: 30%;
  }
}
@media screen and (max-width: 716px) {
  .video {
    width: 90%;
  }
  p {
    font-size: 4vw;
  }
  .underContainer {
    width: 40%;
  }
  .btn-secondary {
    padding: 1.5vw;
    font-size: 4vw;
  }
  .btn-link-branch {
    width: 40%;
  }
}
@media screen and (max-width: 414px) {
}
@media screen and (max-width: 320px) {
}
</style>
