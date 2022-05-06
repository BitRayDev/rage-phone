<template>
  <div class="settings-control">
    <div class="settings-control__section">
      <img class="settings-control__icon" :src="icon"/>
      <p class="settings-control__title">{{title}}</p>
    </div>
    <slot/>
  </div>
</template>

<script>
export default {
  name: "SettingsControlWrapper",
  props: {
    icon: String,
    title: String
  }
}
</script>

<style lang="scss" scoped>
.settings-control {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: .5vw;

  padding: .5vw .5vw;

  background-color: white;
  border-radius: .5vw;

  &__section {
    display: flex;
    align-items: center;
    gap: .5vw;
  }

  &__icon {
    height: 1.5vw;
    width: 1.5vw;
    border-radius: .25vw;
  }

  &__title {
    color: #200E32;

    font-size: .85vw;
    font-weight: 600;
  }


}
</style>