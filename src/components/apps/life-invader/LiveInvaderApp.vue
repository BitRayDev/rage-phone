<template>
  <div class="life-invader-app app">
    <p class="life-invader-app__title">LifeInvader</p>
    <img class="life-invader-app__image" src="@/assets/img/life-invader-image.png" />
    <LifeInvaderForm class="life-invader-app__form" :onSubmit="onSubmit"/>
  </div>
</template>

<script>
import LifeInvaderForm from "./LifeInvaderForm";

export default {
  name: "LifeInvaderApp",
  components: {LifeInvaderForm},
  methods: {
    onSubmit: function () {

    }
  }
}
</script>

<style lang="scss" scoped>
.life-invader-app {
  display: flex;
  flex-direction: column;
  gap: 0.4vw;

  background-image: url("../../../assets/img/backgrounds/red.svg");
  background-size: 100% 100%;

  padding: 0.5vw;
  padding-top: 2vw;

  overflow: hidden;

  position: relative;

  *::-webkit-scrollbar {
    width: 0.2vw;
  }

  *::-webkit-scrollbar-track {
    background: #e9e9e9;
  }

  *::-webkit-scrollbar-thumb {
    background: #b3b3b3;
  }

  &__title {
    color: white;

    font-size: 1.5vw;
    font-weight: 700;

    line-height: 1;
  }

  &__image {
    position: relative;
    z-index: 1;
  }

  &__form {
    position: absolute;
    bottom: 0;
    left: 0;

    width: 100%;
  }
}
</style>