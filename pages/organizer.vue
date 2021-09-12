<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <p class="title">เกี่ยวกับผู้จัดทำ</p>
      <div class="mt-4 boxCard">
        <b-card v-for="(item, index) in organizer" :key="index" class="card">
          <b-row no-gutters>
            <b-col md="3">
              <b-card-img
                :src="item.picture"
                alt="Image"
                class="rounded-1"
              ></b-card-img>
            </b-col>
            <b-col md="8">
              <b-card-text class="rightBox">
                <span class="name"> {{ item.name }}</span> <br />
                <span>{{ item.faculty }} </span> <br />
                <span>{{ item.branch }}</span> <br />
                <span>{{ item.university }}</span> <br />
                <span>{{ item.email }}</span> <br />
              </b-card-text>
            </b-col>
          </b-row>
        </b-card>
      </div>
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
      organizer: [
        {
          name: 'ดุลยภาพ ศรีอำนวย',
          faculty: 'นักศึกษา คณะเทคโนโลยีสารสนเทสและนวัตกรรม',
          branch: 'สาขาวิชา เทคโนโลยีสารสนเทศและนวัตรกรรม',
          university: 'มหาวิทยาลัยกรุงเทพ',
          email: 'E-mail : mingplagad@gmail.com',
          picture: require('@/assets/ming.png'),
        },
        {
          name: 'เธียรนรา อิทธิปาทานันท์',
          faculty: 'นักศึกษา คณะเทคโนโลยีสารสนเทสและนวัตกรรม',
          branch: 'สาขาวิชา เทคโนโลยีสารสนเทศและนวัตรกรรม',
          university: 'มหาวิทยาลัยกรุงเทพ',
          email: 'E-mail : ihqharain@gmail.com',
          picture: require('@/assets/tien.png'),
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
.rightBox {
  font-size: 1.7vw;
  padding: 1px;
  margin-left: 5%;
  margin-top: 2%;
  width: 100%;
}
.boxCard {
  width: 75%;
}
.card {
  margin-bottom: 2%;
}
.bigContainer {
  justify-content: center;
  align-items: center;
  padding: 80px;
  display: flex;
  flex-direction: column;
}
span.name {
  color: #feb249;
  font-size: 1.9vw;
}
.title {
  font-weight: bold;
  font-size: 3.2vw;
  text-align: center;
  color: #53d3d1;
}
@media screen and (max-width: 1150px) {
  .title {
    font-size: 5vw;
  }
  .bigContainer {
    padding: 40px;
    margin-top: 8vh;
  }
  .rightBox {
    font-size: 2.5vw;
  }
  span.name {
    font-size: 2.7vw;
  }
  .boxCard {
    width: 95%;
  }
  .card {
    margin-bottom: 5%;
  }
}
@media screen and (max-width: 716px) {
  .title {
    font-size: 6vw;
  }
  .rightBox {
    margin-top: 5%;
  }
  .bigContainer {
    padding: 20px;
    margin-top: 3vh;
  }
  .rightBox {
    font-size: 4vw;
  }
  span.name {
    font-size: 4.2vw;
  }
  .boxCard {
    width: 80%;
  }
  .card {
    margin-bottom: 10%;
  }
}
</style>
