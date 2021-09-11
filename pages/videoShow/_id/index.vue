<template>
  <div>
    <Header />
    <div class="body">
      <video width="70%" controls="controls" autoplay="autoplay" id="myVideo" @play="playVideo" @pause="pauseVideo">
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
  methods: {
      playVideo(){
          console.log("PLAY")
      },
      pauseVideo(){
          console.log("PAUSE")
      }
  },
}
</script>
<style scoped>
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
  padding: 25px;
  font-family: 'Sukhumvit';
  font-size: 25px;
  border-radius: 10px;
  margin-top: 40px;
}
.btn-link {
  width: 35%;
}
</style>
