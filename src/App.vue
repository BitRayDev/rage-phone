<template>
	<div id="app">
		<IPhone>
			<HomeScreen :apps="apps" :hotbarApps="hotbarApps" :notification="notification" :onAppClick="onAppClick" v-if="currentScreen === 'HOME'"></HomeScreen>
			<RadioScreen v-if="currentScreen === 'RADIO'"></RadioScreen>
			<GarageScreen v-if="currentScreen === 'GARAGE'"></GarageScreen>
			<BankingScreen v-if="currentScreen === 'BANKING'"></BankingScreen>
      <!-- <WhatsAppScreen></WhatsAppScreen> -->
		</IPhone>
	</div>
</template>

<script>
import IPhone from "./components/IPhone.vue";
import HomeScreen from "./components/screens/HomeScreen.vue";
import RadioScreen from "./components/screens/RadioScreen.vue";

import appstoreIcon from "./assets/img/app-icons/appstore.svg";
import bankingIcon from "./assets/img/app-icons/banking.svg";
import callIcon from "./assets/img/app-icons/call.svg";
import garageIcon from "./assets/img/app-icons/garage.svg";
import iMessageIcon from "./assets/img/app-icons/imessage.svg";
import instagramIcon from "./assets/img/app-icons/instagram.svg";
import lifeInvaderIcon from "./assets/img/app-icons/life-invader.svg";
import profileIcon from "./assets/img/app-icons/profile.svg";
import radioIcon from "./assets/img/app-icons/radio.svg";
import settingsIcon from "./assets/img/app-icons/settings.svg";
import shopIcon from "./assets/img/app-icons/shop.svg";
import twitterIcon from "./assets/img/app-icons/twitter.svg";
import whatsupIcon from "./assets/img/app-icons/whatsup.svg";
import GarageScreen from "./components/screens/GarageScreen.vue";
import BankingScreen from "./components/screens/BankingScreen.vue";
import WhatsAppScreen from './components/screens/WhatsAppScreen.vue';

export default {
	name: "App",

	components: {
		IPhone,
		HomeScreen,
		RadioScreen,
		GarageScreen,
		BankingScreen,
    WhatsAppScreen
	},

  methods: {
    onAppClick: function(screenName) {
      this.currentScreen = screenName;
    }
  },

	data: function () {
		return {
      currentScreen: "HOME",
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
					label: "LIFEINVADER",
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
					label: "WHATSUP",
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
					label: "APP STORE",
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
};
</script>

<style lang="scss">
</style>
