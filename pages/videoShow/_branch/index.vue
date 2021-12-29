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
        <source
          src="https://res.cloudinary.com/smilejob/video/upload/v1640095354/IT_kjnhxy.mp4"
          type="video/mp4"
        />
      </video>
      <video
        v-if="branch == 'สาขาวิชาเกมและสื่อเชิงโต้ตอบ'"
        class="video"
        controls="controls"
        @ended="endedVideo"
      >
        <source
          src="https://res.cloudinary.com/smilejob/video/upload/v1640095395/GIM_e1p5qh.mp4"
          type="video/mp4"
        />
      </video>
      <video
        v-if="branch == 'สาขาวิชาวิทยาการคอมพิวเตอร์'"
        class="video"
        controls="controls"
        @ended="endedVideo"
      >
        <source
          src="https://res.cloudinary.com/smilejob/video/upload/v1640095360/CS_mjyc6j.mp4"
          type="video/mp4"
        />
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
      <nuxt-link
        class="btn-link"
        :to="{
          path: `/jobEachBranch/${branch}`,
        }"
      >
        <b-button style="color: black">อาชีพหลังจบการศึกษา</b-button>
      </nuxt-link>
    </div>
       <Footer />
  </div>
</template>
<script>
import Header from '@/components/header'
import Footer from '@/components/footer'
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
        path: `/jobEachBranch/${this.branch}`,
      })
    },
  },
}
</script>
<style scoped>
html,
.body {
  min-height: 100%;
   margin-bottom: 5%;
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
.btn-secondary {
  background-color: #feb249;
  border-color: #feb249;
  width: 100%;
  padding: 1vw;
  font-size: 2vw;
  border-radius: 10px;
  margin-top: 20%;
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
.btn-link {
  width: 25%;
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
  .btn-link {
    width: 30%;
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
  .btn-link {
    width: 35%;
  }
  .title {
    color: #feb249;
    font-weight: bold;
    font-size: 4vw;
    margin-bottom: 7%;
  }
}

@media screen and (max-width: 414px) {
  .btn-link {
    width: 45%;
  }
}
</style>
