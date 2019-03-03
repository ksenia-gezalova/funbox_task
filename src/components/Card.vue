<template>
  <div class="card">
    <div
      class="card__border"
      :class="{'card__border--disabled': disabled, 'card__border--active': isActive }"
    >
      <div
        class="card__container"
        :class="{'card__container--disabled': disabled }"
        @click="isActive = (disabled || isActive) ? false : true"
      >
        <p class="card__good">{{ title }}</p>
        <p class="card__bad">Котэ не одобряет?</p>
        <h2 class="card__title">{{ name }}</h2>
        <span class="card__consist">{{ product }}</span>
        <span class="card__text">{{ amount }}</span>
        <span class="card__text">{{ gift }}</span>
        <span class="card__text" v-if="note">{{ note }}</span>
        <div class="card__img">
          <img src="../assets/Photo.png" alt="Cat photo">
          <div
            class="card__weight"
            :class="{'card__weight--disabled': disabled, 'card__weight--active': isActive }"
          >
            <span>{{ weight }}</span>
            <span>кг</span>
          </div>
        </div>
      </div>
    </div>
    <span v-if="isActive" class="card__link">{{ description }}</span>
    <span v-else-if="disabled" class="card__link card__link--disabled">{{ disabled }}</span>
    <span v-else class="card__link">
      Чего сидишь? Порадуй котэ,
      <b @click="isActive = true">купи</b>
    </span>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: [
    "title",
    "name",
    "product",
    "amount",
    "gift",
    "note",
    "weight",
    "disabled",
    "description"
  ],
  data() {
    return {
      isActive: false
    };
  }
};
</script>

<style lang="scss" scoped>
.card {
  &__bad {
    display: none;
    color: #d91667;
  }
  &__border {
    -webkit-clip-path: polygon(14% 0, 100% 0, 100% 100%, 0 100%, 0 9%);
    clip-path: polygon(14% 0, 100% 0, 100% 100%, 0 100%, 0 9%);
    background-color: #1698d9;
    padding: 4px;
    border-radius: 15px;
    cursor: pointer;
    transition: 0.3s;
    @media (min-width: 768px) {
      margin-right: 20px;
      margin-bottom: 20px;
    }

    &--active {
      background-color: #d91667;

      &:hover {
        .card__good {
          display: none;
        }
        .card__bad {
          display: block;
        }
      }
    }

    &--disabled {
      background-color: #b7b7b7;
      cursor: not-allowed;
    }
  }
  &__container {
    -webkit-clip-path: polygon(14% 0, 100% 0, 100% 100%, 0 100%, 0 9%);
    clip-path: polygon(14% 0, 100% 0, 100% 100%, 0 100%, 0 9%);
    background-color: #f2f2f2;
    width: 265px;
    height: 470px;
    color: #000000;
    padding-top: 6px;
    padding-left: 45px;
    border-radius: 15px;
    position: relative;
    overflow: hidden;
    &--disabled {
      opacity: 0.5;
      cursor: not-allowed;
    }
  }

  &__good,
  &__bad {
    font-size: 15px;
    margin-bottom: 6px;
  }

  &__title {
    margin: 0;
    font-size: 48px;
    font-family: "Trebuchet MS";
    margin-left: -3px;
  }

  &__consist {
    font-family: "Trebuchet MS";
    display: block;
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 13px;
  }

  &__text {
    display: block;
    font-size: 14px;
  }
  &__img {
    position: absolute;
    left: 0px;
    bottom: -4px;
  }
  &__weight {
    position: absolute;
    background-color: #1698d9;
    z-index: 10;
    color: #fff;
    height: 80px;
    width: 80px;
    border-radius: 100%;
    right: -38px;
    bottom: 13px;
    font-family: "Trebuchet MS";
    text-align: center;

    &--active {
      background-color: #d91667;
    }

    &--disabled {
      background-color: #b7b7b7;
    }

    span {
      display: block;
      &:first-child {
        font-size: 41px;
        margin-top: 8px;
        margin-bottom: 0;
      }
      font-size: 24px;
      margin-top: -10px;
    }
  }

  &__link {
    display: block;
    text-align: center;
    font-size: 13px;
    margin-bottom: 20px;
    margin-top: 10px;

    &--disabled {
      color: #d1d152;
    }

    b {
      display: inline-block;
      cursor: pointer;
      font-weight: 100;
      color: #1698d9;
      text-decoration: underline;
      text-decoration-style: dashed;
    }
  }
}
</style>


