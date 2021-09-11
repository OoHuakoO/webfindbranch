<template>
  <div>
    <Header />
    <div class="body">
      <video
        width="60%"
        controls="controls"
        id="myVideo"
        @play="playVideo"
        @pause="pauseVideo"
      >
        <source :src="require('@/assets/testVideo.mp4')" type="video/mp4" />
      </video>
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
  methods: {
    playVideo() {
      console.log('PLAY')
    },
    pauseVideo() {
      console.log('PAUSE')
    },
  },
}
</script>
<style scoped>
* {
  font-family: 'Sukhumvit';
}
p {
  font-weight: bold;
  font-size: 25px;
}
.test {
  position: absolute;
  z-index: 1;
  font-size: 30px;
}
.yellowText {
  color: #feb249;
}
.textPromote {
  text-align: center;
}
.underContainer {
  width: 25%;
  margin-bottom: 100px;
  margin-left: 80px;
}
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 50%;
  align-items: center;
  margin-top: 5%;
}
.body {
  justify-content: center;
  align-items: center;
  padding: 50px;
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
}
.btn-link {
  width: 100%;
}
</style>
