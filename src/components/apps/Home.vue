<template>
	<div class="home-app app">
		<div class="home-app__notification-widget notification-widget" v-if="notification">
			<img class="notification-widget__icon" :src="notification.icon" />
			<div class="notification-widget__text-container">
				<div class="notification-widget__header">
					<p class="notification-widget__title">{{notification.title}}</p>
					<p class="notification-widget__time">{{notification.time}}</p>
				</div>
				<p class="notification-widget__text">{{notification.text}}</p>
			</div>
		</div>
		<div class="home-app__apps">
			<AppButton
				v-for="(app, index) in apps"
				:key="index"
				:icon="app.icon"
				:label="app.label"
        @click.native="() => onAppClick(app.label)"
			></AppButton>
		</div>
		<div class="home-app__hotbar">
			<div class="home-app__hotbar-apps">
				<AppButton v-for="(app, index) in hotbarApps" :key="index" :icon="app.icon" @click.native="() => onAppClick(app.label)"></AppButton>
			</div>
		</div>
	</div>
</template>

<script>
import appstoreIcon from "../../assets/img/icons/apps/appstore.svg";
import bankingIcon from "../../assets/img/icons/apps/banking.svg";
import callIcon from "../../assets/img/icons/apps/call.svg";
import garageIcon from "../../assets/img/icons/apps/garage.svg";
import iMessageIcon from "../../assets/img/icons/apps/imessage.svg";
import instagramIcon from "../../assets/img/icons/apps/instagram.svg";
import lifeInvaderIcon from "../../assets/img/icons/apps/life-invader.svg";
import profileIcon from "../../assets/img/icons/apps/profile.svg";
import radioIcon from "../../assets/img/icons/apps/radio.svg";
import settingsIcon from "../../assets/img/icons/apps/settings.svg";
import shopIcon from "../../assets/img/icons/apps/shop.svg";
import twitterIcon from "../../assets/img/icons/apps/twitter.svg";
import whatsupIcon from "../../assets/img/icons/apps/whatsup.svg";

import AppButton from "../AppButton.vue";

export default {
	components: { AppButton },
	data: function () {
		return {
			notification: {
				icon: whatsupIcon,
				title: "What's the occasion?",
				text: "Can you bring a big salad? I'm on dessert duty.",
				time: "3m ago",
			},
			apps: [
				{
					label: "RADIO",
					icon: radioIcon,
				},
				{
					label: "LIFE-INVADER",
					icon: lifeInvaderIcon,
				},
				{
					label: "GARAGE",
					icon: garageIcon,
				},
				{
					label: "BANKING",
					icon: bankingIcon,
				},
				{
					label: "TWITTER",
					icon: twitterIcon,
				},
				{
					label: "PROFILE",
					icon: profileIcon,
				},
				{
					label: "iMESSAGE",
					icon: iMessageIcon,
				},
				{
					label: "WHATSAPP",
					icon: whatsupIcon,
				},
				{
					label: "INSTAGRAM",
					icon: instagramIcon,
				},
			],
			hotbarApps: [
				{
					label: "CALL",
					icon: callIcon,
				},
				{
					label: "APPSTORE",
					icon: appstoreIcon,
				},
				{
					label: "SHOP",
					icon: shopIcon,
				},
				{
					label: "SETTINGS",
					icon: settingsIcon,
				},
			],
		};
	},
	props: {
		onAppClick: Function,
	},
};
</script>

<style lang="scss">
.notification-widget {
	display: flex;
	gap: 0.5vw;

	padding: 0.3vw 0.5vw;

	background-color: rgba(255, 255, 255, 0.8);
	border-radius: 0.8vw;

	&__icon {
		width: 2vw;
	}

	&__text-container {
	}
	&__header {
		display: flex;
	}
	&__title {
		flex-grow: 1;

		font-size: 0.8vw;
		font-weight: 600;

		color: #222222;
	}
	&__time {
		font-size: 0.6vw;
		font-weight: 500;
		white-space: nowrap;

		color: #3f3f3f;
		opacity: 0.5;
	}
	&__text {
		font-size: 0.8vw;
		font-weight: 500;

		color: #3f3f3f;
	}
}

.home-app {
	position: relative;
	width: 100%;
	height: 100%;

	box-sizing: border-box;

	padding: 0.5vw;
	padding-top: 1.5vw;

	background: url("../../assets/img/backgrounds/sea.png");
	background-size: cover;

	&__notification-widget {
		margin-bottom: 0.75vw;
	}

	&__apps {
		display: flex;
		flex-wrap: wrap;
		gap: 0.6vw;
	}

	&__hotbar {
		position: absolute;
		bottom: 0.75vw;

		width: 87%;
		left: 50%;
		transform: translateX(-50%);

		padding: 0.4vw 0.5vw;

		background: rgba(255, 255, 255, 0.07);

		border-radius: 0.7vw;

		backdrop-filter: blur(1.2vw);
	}

	&__hotbar-apps {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
}
</style>