<template>
  <div class="fraction-app app">
    <div class="fraction-app__header">
      <p class="fraction-app__title">FRACTION APP</p>
      <p class="fraction-app__subtitle">Hello, {{ profile.name }}!</p>
    </div>
    <FractionsListScreen @fraction-click="selectFraction" v-if="!currentFraction" :fractions="fractions" />
    <FractionScreen class="fraction-app__fraction-screen" v-if="currentFraction" :fraction="currentFraction"/>
  </div>
</template>

<script>
import FractionsListScreen from "./FractionsListScreen";
import FractionScreen from "./FractionScreen";

export default {
  name: "FractionApp",
  components: {FractionScreen, FractionsListScreen},
  data: function () {
    return {
      profile: {
        name: "Romario Richardson"
      },
      fractions: [
        {
          name: "Los Santos Police Department",
          members: [
            {
              name: "Romario Richardson",
              rank: "Captain",
              phoneNumber: "1337 228 1338",
              isOnline: true,
            },
            {
              name: "Romario Richardson",
              rank: "Captain",
              phoneNumber: "1337 228 1338",
              isOnline: false,
            },
          ]
        }
      ],
      currentFraction: undefined
    };
  },
  methods: {
    selectFraction: function(fraction) {
      this.currentFraction = fraction;
    }
  },
};
</script>

<style lang="scss">
.fractions-members-info {
  display: flex;
  flex-direction: column;
  gap: .2vw;

  &__header {
    display: flex;
    justify-content: space-between;
    align-items: center;

    width: 100%;
  }

  &__title {
    color: #002525;

    font-size: .8vw;
    font-weight: 600;
  }

  &__members-amount {
    color: #002525;

    font-size: .8vw;
    font-weight: 500;
  }

  &__bar {
    width: 100%;
    height: .3vw;

    background: rgba(0, 0, 0, 0.23);
    border-radius: 100vw;

    overflow: hidden;
  }

  &__bar-fill {
    height: 100%;

    background-color: white;
  }
}

.fractions-general-info {
  display: flex;
  flex-direction: column;
  gap: .5vw;

  width: 100%;

  box-sizing: border-box;
  padding: .5vw .75vw;

  background: linear-gradient(93.6deg, #40FFF4 0%, #40C6FF 17.61%, #40A3FF 40.74%, #408CFF 58.35%, #FFA6F6 100%);

  border-radius: .3vw;

  &__title {
    color: #002525;

    font-size: 1vw;
    font-weight: 600;
  }

  &__subtitle {
    color: #002525;

    font-size: .8vw;
    font-weight: 500;
  }
}

.fraction-app {
  display: flex;
  flex-direction: column;
  gap: 0.4vw;

  background: url("../../../assets/img/backgrounds/purple.svg");
  background-size: 100% 100%;

  padding: 0.5vw;
  padding-top: 2vw;

  overflow: hidden;

  *::-webkit-scrollbar {
    width: 0.2vw;
  }

  *::-webkit-scrollbar-track {
    background: #522644;
  }

  *::-webkit-scrollbar-thumb {
    background: #e33ee6;
  }

  &__title {
    font-size: 1.5vw;
    font-weight: 700;

    line-height: 1;
  }

  &__subtitle {
    font-size: 1vw;
    font-weight: 600;
  }

  &__fraction-screen {
    flex-grow: 1;
  }
}
</style>