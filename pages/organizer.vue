<template>
  <div>
    <Header />
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
.body {
  justify-content: center;
  align-items: center;
  padding: 200px;
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
  width: 35%;
  padding: 25px;
  font-family: 'Sukhumvit';
  font-size: 25px;
  border-radius: 10px;
  margin-top: 40px;
}
</style>
