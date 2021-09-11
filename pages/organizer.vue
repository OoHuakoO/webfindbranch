<template>
  <div class="body">
    <Header />
    <div class="bigContainer">
      <p class="title">เกี่ยวกับคณะผู้จัดทำ</p>
      <div class="mt-4 boxCard">
        <b-card
          img-src="https://placekitten.com/300/300"
          img-alt="Card image"
          img-left
          class="mb-3 boxTop"
        >
          <b-card-text>
            <span> ดุลยภาพ ศรีอำนวย</span> <br />
            <span>นักศึกษา คณะเทคโนโลยีสารสนเทสและนวัตรกรรม </span> <br />
            <span>สาขาวิชา เทคโนโลยีสารสนเทศและนวัตรกรรม</span> <br />
            <span>มหาวิทยาลัยกรุงเทพ</span> <br />
            <span>E-mail : mingplagad@gmail.com</span> <br />
          </b-card-text>
        </b-card>
        <b-card
          img-src="https://placekitten.com/300/300"
          img-alt="Card image"
          img-left
          class="mb-3 boxBottom"
        >
          <b-card-text>
            <span>เธียรนรา อิทธิปาทานันท์</span> <br />
            <span>นักศึกษา คณะเทคโนโลยีสารสนเทสและนวัตรกรรม</span> <br />
            <span>สาขาวิชา เทคโนโลยีสารสนเทศและนวัตรกรรม</span> <br />
            <span>มหาวิทยาลัยกรุงเทพ</span> <br />
            <span> E-mail : ihqharain@gmail.com</span> <br />
          </b-card-text>
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
}
</script>
<style scoped>
html,
.body {
  min-height: 100%;
}
.boxTop {
  margin-bottom: 3rem !important;
  padding: 20px;
  font-size: 22px;
}
.boxBottom {
  font-size: 22px;
  padding: 20px;
}
.boxCard {
  width: 80%;
}
.bigContainer {
  justify-content: center;
  align-items: center;
  padding: 80px;
  display: flex;
  flex-direction: column;
}
p {
  font-family: 'Sukhumvit';
}
.title {
  font-weight: bold;
  font-size: 50px;
  text-align: center;
  color: #53d3d1;
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
  margin-top: 40px;
}
.btn-link {
  width: 30%;
}
</style>
