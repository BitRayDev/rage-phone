<template>
  <div class='circle-progress-bar'>
    <div class='circle-progress-bar__circle'>
      <svg class='circle-progress-bar__circle-border' viewBox="0 0 120 120">
        <circle cx="60" cy="60" r="54" fill="none" stroke-width="10"/>
        <circle :style="{boxShadow: `0 0 2vw ${color}` }" pathLength="100" stroke-dasharray="100" :stroke-dashoffset="100 -
                percentValue" cx="60" cy="60" r="54" fill="none" :stroke="color" stroke-width="10"
        />
      </svg>
      <img class='circle-progress-bar__icon' :src="icon"/>
    </div>
    <p class='circle-progress-bar__text-value'>
      <span class="circle-progress-bar__text-value_highlighted">{{ clampedValue }}</span> / {{ maxValue }}
    </p>
  </div>
</template>

<script>
export default {
  name: "CircleProgressBar",
  props: {
    value: Number,
    maxValue: Number,
    icon: String,
    color: String,
  },
  computed: {
    clampedValue: function () {
      let clampedValue;
      if (this.value > 100)
        clampedValue = 100;
      else if (this.value < 0)
        clampedValue = 0;
      else
        clampedValue = this.value;

      return clampedValue;
    },
    percentValue: function () {
      return this.clampedValue / this.maxValue * 100;
    }
  }
}
</script>

<style lang="scss" scoped>
.circle-progress-bar {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: .25vw;

  &__circle {
    display: flex;
    justify-content: center;
    align-items: center;

    width: 3vw;
    height: 3vw;

    position: relative;
  }

  &__circle-border {
    height: 100%;
    width: 100%;

    position: absolute;
    transform: rotate(90deg);

    stroke: #252833;

    filter: drop-shadow(0px 0px 1.2vw #95E6CB);
  }

  &__icon {
    width: 30%;
  }

  &__text-value {
    color: rgba(255, 255, 255, 0.2);

    font-size: .75vw;
    font-weight: 500;

    &_highlighted {
      color: #3BD738;
    }
  }
}

</style>