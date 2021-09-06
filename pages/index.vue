<template>
  <div>
    <Header />
    <div class="body">
      <h1>กิจกรรมค้นหาวิชาสาขาสำหรับคุณ</h1>
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
.container {
}
.body {
  justify-content: center;
  align-items: center;
  padding: 50px;
  display: flex;
}
</style>
