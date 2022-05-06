<template>
  <div class="settings-app app">
    <p class="settings-app__title">Settings</p>
    <div class="settings-app__header">
      <div class="settings-app__avatar-container">
        <p class="settings-app__initials">{{ profile.initials }}</p>
      </div>
      <div class="settings-app__header-text">
        <p class="settings-app__name">{{ profile.name }}</p>
        <p class="settings-app__description">Here you can edit your phone settings</p>
      </div>
    </div>
    <div class="settings-app__controls">
      <ToggleControl title="AirPlane Mode" :icon="require('@/assets/img/icons/settings/airplane.svg')"/>
      <ToggleControl title="Dark Mode" :icon="require('@/assets/img/icons/settings/moon.svg')"/>
      <SliderControl title="Brightness" :icon="require('@/assets/img/icons/settings/sun.svg')"/>
      <ToggleControl title="Mute Mode" :icon="require('@/assets/img/icons/settings/mute.svg')"/>
    </div>
  </div>
</template>

<script>
import SliderControl from "./SliderControl";
import ToggleControl from "./ToggleControl";
export default {
  name: "SettingsApp",
  components: {ToggleControl, SliderControl},
  data: function () {
    return {
      profile: {
        initials: "RR",
        name: "Richard Rodrigoes"
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.settings-app {
  display: flex;
  flex-direction: column;
  gap: 0.4vw;

  background: #f1f1f1;
  background-size: 100% 100%;

  padding: 0.5vw;
  padding-top: 2vw;

  overflow: hidden;

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
    color: #200e32;

    font-size: 1.5vw;
    font-weight: 700;

    line-height: 1;
  }

  &__header {
    display: flex;
    gap: .5vw;

    padding: .4vw .5vw;

    background-color: white;
    border-radius: .5vw;
  }

  &__initials {
    font-size: 1.2vw;
    font-weight: 600;
  }

  &__avatar-container {
    display: flex;
    flex-shrink: 0;
    align-items: center;
    justify-content: center;

    height: 3vw;
    width: 3vw;

    background-color: #C6C5CB;
    border-radius: 100vw;
  }

  &__name {
    color: #200E32;

    font-size: 1vw;
    font-weight: 700;
  }

  &__description {
    color: #200E32;

    font-size: .8vw;
    font-weight: 500;
  }

  &__controls {
    display: flex;
    flex-direction: column;
    gap: .25vw;
  }
}
</style>