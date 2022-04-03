<template>
	<div class="calling-screen">
		<p class="calling-screen__title">Calling</p>
		<div class="calling-screen__contact-info">
			<img class="calling-screen__contact-avatar" :src="contact.avatar"/>
			<p class="calling-screen__contact-name">{{contact.name}}</p>
			<p class="calling-screen__contact-phone-number">{{contact.phone}}</p>
		</div>
		<div class="calling-screen__control-buttons">
			<div class="calling-screen__control-button calling-control-button">
				<img class="calling-control-button__icon" src="@/assets/img/icons/volume.svg" />
			</div>
			<div
				class="calling-screen__control-button calling-control-button calling-control-button_type_hang-up"
				@click="onHangUpButtonClick"
			>
				<img class="calling-control-button__icon" src="@/assets/img/icons/hang-up.svg" />
			</div>
			<div class="calling-screen__control-button calling-control-button">
				<img class="calling-control-button__icon" src="@/assets/img/icons/microphone-off.svg" />
			</div>
		</div>
	</div>
</template>

<script>
import avatar from '../../../assets/img/avatar.png';

export default {
	data: function () {
		return {
			contact: {
				name: "Angelika Richardson",
        phone: "+8800 666 555 21",
        avatar: avatar
			},
		};
	},

	methods: {
		onHangUpButtonClick: function () {
			// TODO: Handle hang-up button click;
		},
	},
};
</script>

<style lang="scss">
.calling-control-button {
	display: flex;
	align-items: center;
	justify-content: center;

	width: 3.5vw;
	height: 3.5vw;

	background-color: #ecebec;

	border-radius: 100vw;

	&_type {
		&_hang-up {
			background-color: #fc3e30;

			transition: filter 100ms ease-out;
			&:hover {
				filter: drop-shadow(0 0 0.25vw #fc3e3080);
			}
		}
	}

	&__icon {
		width: 1.6vw;
	}
}

.calling-screen {
	display: flex;
	flex-direction: column;
	align-items: center;
  justify-content: space-between;
	gap: 0.4vw;

	height: 100%;

	background-color: #f1f1f1;

  box-sizing: border-box;
	padding: 0.5vw;
	padding-top: 2vw;
  padding-bottom: 3vw;

	overflow: hidden;

	&__title {
		width: 100%;

		font-size: 1.5vw;
		font-weight: 700;

		line-height: 1;

		color: #200e32;
	}

  &__contact-info {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: .2vw;
  }

  &__contact-avatar {
    width: 8vw;

    border-radius: 100vw;
  }

  &__contact-name {
    font-size: .9vw;
    font-weight: 600;

    color: #200E32;
  }
  &__contact-phone-number {
    font-size: .8vw;

    color: #200E32;
  }

	&__control-buttons {
		display: flex;
		justify-content: space-around;

		width: 100%;
	}
}
</style>