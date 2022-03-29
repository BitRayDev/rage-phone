<template>
	<div class="iphone">
		<img class="iphone__bangs" src="@/assets/img/iphone-bangs.svg" />
    <div class="iphone__status-bar status-bar">
      <div class="status-bar__section">
        <img class="status-bar__wifi-icon" src="@/assets/img/icons/wifi.svg">
        <p class="status-bar__label">C-OS</p>
      </div>
      <div class="status-bar__section">
        <img class="status-bar__battery-icon" src="@/assets/img/icons/battery.svg">
        <p class="status-bar__battery-value">100%</p>
      </div>
    </div>
		<div class="iphone__view">
			<slot />
		</div>
	</div>
</template>

<script>
export default {};
</script>

<style lang="scss">
.status-bar {
  display: flex;
  justify-content: space-between;

  height: 1vw;
  width: 100%;

  &__section {
    display: flex;
    align-items: center;

    gap: .25vw;
  }

  &__battery-icon, &__wifi-icon  {
    height: 55%;
  }

  &__battery-value, &__label {
    font-size: .8vw;
  }
}

.iphone {
	position: absolute;
	right: 2vw;
	bottom: 2vw;

	width: 17vw;
	height: 32vw;

	box-sizing: border-box;
	padding: 1vw;

	color: white;
	background: url("../assets/img/iphone.svg");
	background-repeat: no-repeat;
	background-size: 100% 100%;
	resize: both;

	&__bangs {
		position: absolute;
    z-index: 1;

    width: 35%;

		left: 50%;
		transform: translateX(-50%);
	}

  &__status-bar {
    position: absolute;
    z-index: 1;

    left: 50%;
    transform: translateX(-50%);

    width: 75%;
  }

	&__view {
    position: relative;

		width: 100%;
		height: 100%;

		border-radius: 1.5vw;

		overflow: hidden;
	}
}
</style>