<template>
  <div class="life-invader-form">
    <div class="life-invader-form__header">
      <p class="life-invader-form__title">Type your message here</p>
      <p class="life-invader-form__subtitle">1597$ per message</p>
      <p class="life-invader-form__subtitle">150 symbols</p>
    </div>
    <textarea class="life-invader-form__input" v-model="inputValue"/>
    <div class="life-invader-form__submit-container">
      <Button theme="banking" @click.native="onSubmit">Send It</Button>
      <div class="life-invader-form__anonim-container">
        <p class="life-invader-form__anonim-label">Anonim</p>
        <input class="life-invader-form__anonim-checkbox" type="checkbox"/>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "../../Button.vue";

export default {
  name: "LifeInvaderForm",
  components: {Button},
  data: function () {
    return {
      inputValue: "",
    };
  },
  props: {
    onSubmit: Function
  }
};
</script>

<style lang="scss">
.life-invader-form {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: .5vw;

  box-sizing: border-box;
  padding: 0.5vw 0.75vw;

  background-color: #fcfcfc;
  border-radius: 1vw 1vw 0 0;

  &__header {
    display: flex;
    flex-direction: column;
    gap: .2vw;

    width: 100%;
  }

  &__title {
    color: black;

    font-size: 0.9vw;
    font-weight: 700;
  }

  &__subtitle {
    color: #87898d;

    font-size: 0.7vw;
    font-weight: 500;
  }

  &__input {
    width: 100%;
    height: 5vw;

    box-sizing: border-box;
    padding: 0.5vw 0.75vw;

    font-size: 0.85vw;

    background-color: white;

    border: none;
    border-radius: 1vw;
    outline: none;

    resize: none;
  }

  &__submit-container {
    display: flex;
    align-items: center;
    width: 100%;
    gap: .75vw;
  }

  &__anonim-container {
    display: flex;
    align-items: center;
    gap: .5vw;
  }

  &__anonim-label {
    color: #252525;

    font-size: 1vw;
    font-weight: 500;
  }

  &__anonim-checkbox {
    width: 1.25vw;
    height: 1.25vw;

    border: .1vw solid #C7C7C7;
    border-radius: 100vw;

    -webkit-appearance: none;
    outline: none;

    &:checked {
      &::before {
        content: "";
        display: block;

        width: 100%;
        height: 100%;

        background-image: url("../../../assets/img/icons/mark.svg");
        background-size: 75%;
        background-position: center;
        background-repeat: no-repeat;
      }
    }
  }
}
</style>