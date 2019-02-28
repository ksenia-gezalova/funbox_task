<template>
  <div class="main">
    <h1 class="main__title">Ты сегодня покормил кота?</h1>
    <Card></Card>
  </div>
</template>

<script>
import Card from './Card'
export default {
  name: 'Main',
  components: {
    Card
  }
}
</script>

<style lang="scss" scoped>
.main {
  min-width: 320px;
  background-image: url('../assets/Pattern.png');
  background-attachment: fixed;
  height: 100vh;
  color: #ffffff;
  padding-top: 40px;
  overflow: hidden;

  &__title {
    font-weight: 300;
    text-align: center;
  }
}
</style>
