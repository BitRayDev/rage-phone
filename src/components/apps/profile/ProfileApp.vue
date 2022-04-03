<template>
	<div class="app profile-app">
		<div class="profile-app__title">Profile</div>
		<div class="profile-app__option profile-option">
			<img class="profile-option__icon" :src="profile.avatar" />
			<div class="profile-option__text">
				<p class="profile-option__name">{{profile.name}}</p>
				<p class="profile-option__value">{{profile.phoneNumber}}</p>
			</div>
		</div>
		<div class="profile-app__options">
			<div class="profile-app__option profile-option" v-for="option in options">
				<img class="profile-option__icon" src="@/assets/img/icons/car.svg" />
				<div class="profile-option__text">
					<p class="profile-option__name">{{option.name}}</p>
					<p class="profile-option__value">{{option.value}}</p>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import avatar from '../../../assets/img/avatar1.png';

import diamondIcon from '../../../assets/img/icons/diamond.svg';
import animalIcon from '../../../assets/img/icons/animal.svg';
import carIcon from '../../../assets/img/icons/car.svg';
import boatIcon from '../../../assets/img/icons/boat.svg';
import houseIcon from '../../../assets/img/icons/house.svg';
import moneyIcon from '../../../assets/img/icons/coins.svg';
import marriageIcon from '../../../assets/img/icons/marriage.svg';

export default {
	data: function () {
		return {
      profile: {
        avatar: avatar,
        name: "Romario Richardson",
        phoneNumber: "8 8800 555 35 35"
      },
			options: [
				{
          icon: diamondIcon,
					name: "Vip-Status",
					value: "Yes",
				},
				{
          icon: animalIcon,
					name: "Animals",
					value: "Yes",
				},
				{
          icon: carIcon,
					name: "Cars",
					value: "Yes",
				},
				{
          icon: boatIcon,
					name: "Boats",
					value: "Yes",
				},
				{
          icon: houseIcon,
					name: "House",
					value: "Yes",
				},
				{
          icon: moneyIcon,
					name: "Cash money",
					value: "$650 000 000",
				},
				{
          icon: moneyIcon,
					name: "Bank money",
					value: "$650 000 000",
				},
				{
          icon: marriageIcon,
					name: "Married",
					value: "Yes",
				},
			],
		};
	},
};
</script>

<style lang="scss">
.profile-option {
	display: flex;
	align-items: center;
	gap: 0.4vw;

	padding: 0.6vw 0.75vw;

	background: white;

	border: 0.1vw solid #ffffff20;
	border-radius: 0.5vw;

	transition: filter 100ms ease-out;
	&:hover {
		filter: drop-shadow(0 0 0.5vw rgba(197, 197, 197, 0.5));
	}

	&__icon {
		width: 2.5vw;

    border-radius: .25vw;
	}
	&__text {
		display: flex;
		flex-direction: column;
		gap: 0.1vw;
	}
	&__name {
    color: #200E32;

		font-size: 0.9vw;
		font-weight: 600;
	}

	&__value {
		font-size: 0.8vw;
		font-weight: 500;

		color: #200E32;
	}
}

.profile-app {
	display: flex;
	flex-direction: column;
	gap: 0.5vw;

	background: #F1F1F1;
	background-size: 100% 100%;

	padding: 0.5vw;
	padding-top: 2vw;
	padding-bottom: 0;

	&__title {
    color: #200E32;

		font-size: 1.5vw;
		font-weight: 700;

		line-height: 1;
	}

	&__options {
		display: flex;
		flex-direction: column;

		flex-grow: 1;

		padding-right: 0.25vw;
		padding-bottom: 0.5vw;

		overflow: auto;

		gap: 0.4vw;

		&::-webkit-scrollbar {
			width: 0.2vw;
		}
		&::-webkit-scrollbar-track {
			background: #e9e9e9;
		}
		&::-webkit-scrollbar-thumb {
			background: #b3b3b3;
		}
	}

	&__option {
	}
}
</style>