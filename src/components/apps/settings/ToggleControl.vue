<template>
  <SettingsControlWrapper :icon="icon" :title="title">
    <input class="toggle-control__input" type="checkbox" @change="onToggle"/>
  </SettingsControlWrapper>
</template>

<script>
import SettingsControlWrapper from "./SettingsControlWrapper";

export default {
  name: "ToggleControl",
  components: {SettingsControlWrapper},
  props: {
    icon: String,
    title: String,
    onToggle: Function
  }
}
</script>

<style lang="scss" scoped>
.toggle-control {
  &__input {
    position: relative;

    width: 2.4vw;
    height: 1.5vw;

    background-color: #F3F3F3;
    border-radius: 100vw;

    -webkit-appearance: none;

    &::before {
      content: "";
      display: block;

      width: 1vw;
      height: 1vw;

      position: absolute;
      top: .25vw;
      left: .25vw;

      background-color: #C6C5CB;
      border-radius: 100vw;

      transition: left 100ms ease-out, background-color 100ms ease-out;
    }

    &:checked {
      &::before {
        left: 1vw;
        background-color: #52EE58;
      }
    }
  }
}
</style>