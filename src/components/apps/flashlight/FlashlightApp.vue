<template>
	<div class="flashlight app">
		<p class="flashlight__title">Flashlight</p>
		<div class="flashlight__content">
			<img class="flashlight__icon" src="@/assets/img/icons/flashlight.svg" />
			<div class="flashlight__control">
				<div
					:class="`flashlight__control-section ${ section > sectionsAmount-value ? 'flashlight__control-section_active' : ''}`"
					v-for="section in sectionsAmount"
				></div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data: function () {
		return {
			value: 3,
			sectionsAmount: 5,
		};
	},
};
</script>

<style lang="scss">
.flashlight {
  display: flex;
  flex-direction: column;

	background: url("../../../assets/img/backgrounds/flashlight.png");
	background-size: 100% 100%;

  padding: 0.5vw;
  padding-top: 2vw;

	&__title {
    color: #200E32;

		font-size: 1.5vw;
		font-weight: 700;

		line-height: 1;
	}

  &__icon {
    height: 2vw;
  }

  &__content {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    justify-content: center;
    align-items: center;
    gap: 1vw;
  }

  &__control {
    display: flex;
    flex-direction: column;
    gap: .25vw;
  }

  &__control-section {
    background: rgba(21, 21, 21, 0.28);
    width: 7vw;
    height: 3vw;

    &:first-child {
      border-radius: 1vw 1vw 0 0;
    }
    &:last-child {
      border-radius: 0 0 1vw 1vw;
    }

    &_active {
      background: rgba(255, 255, 255, 0.28);
    }
  }
}
</style>