<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <nuxt-link class="leftContainer" to="/seeJob">
        <div class="boxImage">
          <img
            src="https://bahmansport.com/media/com_store/images/empty.png"
            alt="Image"
            class="leftImg"
          />
        </div>
        <p class="jobAfterLearn">อาชีพหลังจบการอาชีพหลังจบการศึกษา</p>
      </nuxt-link>
      <div class="rightContainer">
        <p class="textSeeVideo">ดูวีดีโอสาขาอื่นๆ</p>
        <nuxt-link
          v-for="(item, index) in itemOtherVideo"
          :key="index"
          class="rowVideo"
          :to="`/videoShow/${item.name}`"
        >
          <img :src="item.picture" alt="Image" class="rightImg" />
          <div class="boxTextVideo">
            <span>{{ item.name }}</span>
          </div>
        </nuxt-link>
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
export default {
  components: {
    Header,
  },
  data() {
    return {
      itemOtherVideo: [
        {
          name: 'สาขาวิชาเกมและสื่อเชิงโต้ตอบ',
          picture: 'https://bahmansport.com/media/com_store/images/empty.png',
        },
        {
          name: 'สาขาวิชาวิทยาการคอมพิวเตอร์',
          picture: 'https://bahmansport.com/media/com_store/images/empty.png',
        },
        {
          name: 'สาขาวิชาเทคโนโลยีสารสนเทศ',
          picture: 'https://bahmansport.com/media/com_store/images/empty.png',
        },
        {
          name: 'สาขาวิชาวิทยาการคอมพิวเตอร์ความปลอดภัยทางไซเบอร์',
          picture: 'https://bahmansport.com/media/com_store/images/empty.png',
        },
      ],
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
.textSeeVideo {
  font-size: 2vw;
}
.rowVideo {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-bottom: 5%;
  text-decoration: none;
}
.leftImg {
  width: 100%;
  height: 100%;
  border-radius: 20px;
}
.rightImg {
  width: 40%;
  border-radius: 10px;
}
.jobAfterLearn {
  font-size: 2vw;
  font-weight: 600;
  margin-top: 5%;
  color: #101010;
}
.bigContainer {
  padding: 8vh 10vw 1vh 10vw;
  display: flex;
  flex-direction: row;
}
.leftContainer {
  width: 60%;
  align-items: center;
  display: flex;
  flex-direction: column;
  text-decoration: none;
}
.rightContainer {
  width: 40%;
  margin-left: 5%;
}
.boxTextVideo {
  justify-content: center;
  align-items: center;
  display: flex;
  width: 60%;
  font-size: 1.5vw;
  margin-left: 5%;
  text-align: center;
  border-left: solid 2px #feb249;
  padding: 10px;
  color: #feb249;
}
.boxImage {
  padding: 2vw;
  background-color: #53d3d1;
  border-radius: 20px;
  cursor: pointer;
  width: 100%;
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
.underContainer {
  width: 25%;
  margin-bottom: 4%;
  margin-left: 7%;
}
@media screen and (max-width: 1150px) {
  .bigContainer {
    padding: 8vh 10vw 1vh 10vw;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .leftContainer {
    width: 80%;
    align-items: center;
    display: flex;
    flex-direction: column;
    text-decoration: none;
  }
  .rightContainer {
    width: 90%;
    margin-top: 4%;
  }
  .jobAfterLearn {
    font-size: 3.5vw;
    margin-top: 10%;
  }
  .textSeeVideo {
    font-size: 3.5vw;
    margin-bottom: 6%;
  }
  .rightImg {
    width: 45%;
    border-radius: 10px;
  }
  .boxTextVideo {
    font-size: 3.5vw;
    margin-left: 5%;
    padding: 10px;
  }
  .btn-secondary {
    padding: 1.5vw;
    font-size: 3vw;
  }
  .underContainer {
    width: 40%;
    margin-bottom: 10%;
  }
}
@media screen and (max-width: 716px) {
  .btn-secondary {
    font-size: 4vw;
  }
}
</style>
