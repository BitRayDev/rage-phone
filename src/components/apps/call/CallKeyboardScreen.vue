<template>
	<div class="call-keyboard-screen">
		<p class="call-keyboard-screen__title">Type number</p>
		<input class="call-keyboard-screen__input" type="text" v-model="inputValue" autofocus/>
		<div class="call-keyboard-screen__keyboard call-keyboard">
			<div
				class="call-keyboard__number-button"
				v-for="button in buttons"
				@click="onNumberButtonClick(button.number)"
			>
				<p class="call-keyboard__number">{{button.number}}</p>
				<p class="call-keyboard__text">{{button.text}}</p>
			</div>
		</div>
		<div class="call-keyboard-screen__call-button call-button" @click="onCallButtonClick">
			<img class="call-button__icon" src="@/assets/img/icons/call.svg" />
		</div>
	</div>
</template>

<script>
export default {
	data: function () {
		return {
			inputValue: "",
			buttons: [
				{
					number: "1",
					text: "",
				},
				{
					number: "2",
					text: "ABC",
				},
				{
					number: "3",
					text: "DEF",
				},
				{
					number: "4",
					text: "GHI",
				},
				{
					number: "5",
					text: "JKL",
				},
				{
					number: "6",
					text: "MNO",
				},
				{
					number: "7",
					text: "PQRS",
				},
				{
					number: "8",
					text: "TUV",
				},
				{
					number: "9",
					text: "WXYZ",
				},
				{
					number: "*",
					text: "",
				},
				{
					number: "0",
					text: "+",
				},
				{
					number: "#",
					text: "",
				},
			],
		};
	},

	methods: {
		onNumberButtonClick: function (number) {
			this.inputValue += number;
		},
    onCallButtonClick: function() {
      // TODO: Handle call button click;
    }
	},
};
</script>

<style lang="scss">
.call-button {
  display: flex;
  align-items: center;
  justify-content: center;

	width: 3.5vw;
	height: 3.5vw;

  background-color: #3BD738;

	border-radius: 100vw;

  transition: filter 100ms ease-out;
  &:hover {
    filter: drop-shadow(0 0 0.25vw #3BD73880);
  }

  &__icon {
    width: 1.6vw;
  }
}

.call-keyboard {
	display: grid;
	grid-template-columns: 1fr 1fr 1fr;
	gap: 0.5vw;

	margin: 0 auto;

	&__number-button {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;

		width: 3.5vw;
		height: 3.5vw;

		color: #252525;

		border-radius: 100vw;
		border: 0.1vw solid #275988;

		transition: filter 150ms ease-out;
		&:hover {
			filter: drop-shadow(0 0 0.1vw #27598855);
		}
	}
	&__number {
		font-size: 1.75vw;
	}
	&__text {
		font-size: 0.9vw;
	}
}

.call-keyboard-screen {
	display: flex;
	flex-direction: column;
	align-items: center;
	gap: 0.4vw;

	height: 100%;

	background-color: #f1f1f1;

	padding: 0.5vw;
	padding-top: 2vw;

	overflow: hidden;

	&__title {
    width: 100%;

		font-size: 1.5vw;
		font-weight: 700;

		line-height: 1;

		color: #200e32;
	}

	&__input {
		font-size: 2vw;
		text-align: center;

		background: none;
		border: none;
		outline: none;
	}

	&__keyboard {
	}
}
</style>