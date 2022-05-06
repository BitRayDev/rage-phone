<template>
  <SettingsControlWrapper :icon="icon" :title="title">
    <div class="slider-control__input-container">
      <VueSlider  @change="onChange"/>
    </div>
  </SettingsControlWrapper>
</template>

<script>
import VueSlider from 'vue-slider-component'
import 'vue-slider-component/theme/antd.css'
import SettingsControlWrapper from "./SettingsControlWrapper";

export default {
  name: "SliderControl",
  components: {
    SettingsControlWrapper,
    VueSlider
  },
  props: {
    icon: String,
    title: String,
    onChange: Function
  }
}
</script>

<style lang="scss" scoped>
.slider-control {
  &__input-container {
    width: 4vw;
  }
}
</style>