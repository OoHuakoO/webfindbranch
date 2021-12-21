<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <p class="title">{{ branch }}</p>
      <video
        v-if="branch == 'สาขาวิชาเทคโนโลยีสารสนเทศ'"
        class="video"
        controls="controls"
        @ended="endedVideo"
      >
        <source src="https://res.cloudinary.com/smilejob/video/upload/v1640095354/IT_kjnhxy.mp4" type="video/mp4" />
      </video>
      <video
        v-if="branch == 'สาขาวิชาเกมและสื่อเชิงโต้ตอบ'"
        class="video"
        controls="controls"
        @ended="endedVideo"
      >
        <source src="https://res.cloudinary.com/smilejob/video/upload/v1640095395/GIM_e1p5qh.mp4" type="video/mp4" />
      </video>
      <video
        v-if="branch == 'สาขาวิชาวิทยาการคอมพิวเตอร์'"
        class="video"
        controls="controls"
        @ended="endedVideo"
      >
        <source src="https://res.cloudinary.com/smilejob/video/upload/v1640095360/CS_mjyc6j.mp4" type="video/mp4" />
      </video>
      <video
        v-if="
          branch ==
          'สาขาวิชาวิทยาการคอมพิวเตอร์ มุ่งเน้นความมั่นคงปลอดภัยไซเบอร์และวิทยาการข้อมูล'
        "
        class="video"
        controls="controls"
        @ended="endedVideo"
      >
        <source
          src="https://res.cloudinary.com/smilejob/video/upload/v1640095360/DS_zfakqu.mp4"
          type="video/mp4"
        />
      </video>
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
      branch: this.$route.params.branch,
    }
  },
  methods: {
    endedVideo() {
      this.$router.push({
        path: '/showOtherVideo',
      })
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
.title {
  color: #feb249;
  font-weight: bold;
  font-size: 2.5vw;
  margin-bottom: 1%;
  text-align: center;
}
.video {
  width: 52%;
}
.yellowText {
  color: #feb249;
}
.textPromote {
  text-align: center;
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
  padding: 2vw;
  display: flex;
  flex-direction: column;
}
@media screen and (max-width: 1150px) {
  .bigContainer {
    padding: 0vw;
    margin-top: 20vh;
  }
  .video {
    width: 80%;
  }
  .title {
    color: #feb249;
    font-weight: bold;
    font-size: 4vw;
    margin-bottom: 5%;
  }
  .container {
    width: 70%;
    margin-top: 5%;
  }
}
@media screen and (max-width: 716px) {
  .video {
    width: 90%;
  }
  .title {
    color: #feb249;
    font-weight: bold;
    font-size: 4vw;
    margin-bottom: 7%;
  }
}
</style>
