<template>
  <div class="main">
    <div class="main__mask">
      <h1 class="main__title">Ты сегодня покормил кота?</h1>
      <div class="main__wrapper">
        <Card
          v-for="(card, index) in cards"
          :key="index"
          :title="card.title"
          :name="card.name"
          :product="card.product"
          :amount="card.amount"
          :gift="card.gift"
          :note="card.note"
          :weight="card.weight"
          :disabled="card.isDisabled"
          :description="card.description"
        ></Card>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./Card";
export default {
  name: "Main",
  components: {
    Card
  },
  data() {
    return {
      cards: [
        {
          title: "Сказочное заморское явство",
          name: "Нямушка",
          product: "с фуа-гра",
          amount: "10 порций",
          gift: "мышь в подарок",
          note: false,
          weight: "0,5",
          description: "Печень утки разварная с артишоками",
          isDisabled: false
        },
        {
          title: "Сказочное заморское явство",
          name: "Нямушка",
          product: "с рыбой",
          amount: "40 порций",
          gift: "2 мыши в подарок",
          note: false,
          weight: "2",
          description: "Головы щучьи с чесноком да свежайшая сёмгушка",
          isDisabled: false
        },
        {
          title: "Сказочное заморское явство",
          name: "Нямушка",
          product: "с курой",
          amount: "100 порций",
          gift: "5 мышей в подарок",
          note: "заказчик доволен",
          weight: "5",
          description: "Филе из цыплят с трюфелями в бульоне",
          isDisabled: "Печалька, с курой закончился"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.main {
  min-width: 320px;
  background-image: url("../assets/Pattern.png");
  background-attachment: fixed;
  color: #ffffff;
  overflow: hidden;
  padding-bottom: 20px;
  min-height: 100vh;

  @media (min-width: 1200px) {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
  }

  &__mask {
    margin: 0;
    background-color: rgba(0, 0, 0, 0.2);
    padding-top: 40px;
    width: 100%;
  }

  &__title {
    margin: 0;
    font-weight: 100;
    text-align: center;
    font-size: 36px;
    margin-bottom: 20px;
  }

  &__wrapper {
    display: grid;
    justify-content: center;
    align-items: center;
    grid-gap: 30px;

    @media (min-width: 768px) {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: center;
    }
  }
}
</style>
