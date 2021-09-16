<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <video class="video" controls="controls" @ended="endedVideo">
        <source :src="require('@/assets/testVideo.mp4')" type="video/mp4" />
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
p {
  font-weight: bold;
  font-size: 1.8vw;
}
.video {
  width: 70%;
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
  padding: 5vw;
  display: flex;
  flex-direction: column;
}
@media screen and (max-width: 1150px) {
  .bigContainer {
    padding: 0vw;
    margin-top: 25vh;
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
}
@media screen and (max-width: 716px) {
  .video {
    width: 90%;
  }
  p {
    font-size: 4vw;
  }
}
</style>
