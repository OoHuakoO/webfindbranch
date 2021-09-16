<template>
  <div class="body">
    <Header />

    <div class="bigContainer">
      <p class="title">{{ branch }}</p>
      <p class="subtitle">คือสาขาวิชาที่เหมาะกับคุณ</p>
      <img :src="picture" alt="Image" class="rightImg" />
      <p class="moreText">
        รับชมวิดีโอเพื่อทำความรู้จักกับสิ่งที่น่าสนใจของสาขาวิชาได้เลย !
      </p>
      <nuxt-link class="btn-link" to="/videoShow/สาขาวิชาเทคโนโลยีสารสนเทศ">
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
      picture: 'https://bahmansport.com/media/com_store/images/empty.png',
      branch: 'สาขาวิชาเทคโนโลยีสารสนเทศ',
    }
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
  padding: 50px;
  display: flex;
  flex-direction: column;
}
.title {
  font-weight: bold;
  font-size: 4vw;
  text-align: center;
  color: #feb249;
}
.subtitle {
  text-align: center;
  font-weight: 300;
  font-size: 3vw;
}
.moreText {
  text-align: center;
  font-weight: 300;
  font-size: 2.5vw;
  margin-top: 3%;
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
}
</style>
