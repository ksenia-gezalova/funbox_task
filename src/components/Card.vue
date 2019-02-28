<template>
  <div class="card">
    <div class="card__container">
      <p class="card__good">Сказочное заморское явство</p>
      <h2 class="card__title">Нямушка</h2>
      <span class="card__consist">с рыбой</span>
      <span class="card__text">10 порций</span>
      <span class="card__text">мышь в подарок</span>
      <div class="card__img">
        <img src="../assets/Photo.png" alt="Cat photo">
        <div class="card__weight">
          <span>0,5</span>
          <span>кг</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card'
}
</script>

<style lang="scss" scoped>
.card {
  &__container {
    -webkit-clip-path: polygon(13% 0, 100% 0, 100% 100%, 0 100%, 0 10%);
    clip-path: polygon(13% 0, 100% 0, 100% 100%, 0 100%, 0 10%);
    background-color: #f2f2f2;
    width: 280px;
    height: 480px;
    color: #000000;
    padding-top: 25px;
    padding-left: 50px;
    border-radius: 5px;
  }
}
</style>


