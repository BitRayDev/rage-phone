<template>
	<div id="app">
		<IPhone>
			<HomeApp :onAppClick="onAppClick" v-if="isAppActive('Home')"></HomeApp>
			<RadioApp v-if="isAppActive('Radio')"></RadioApp>
			<GarageApp v-if="isAppActive('Garage')"></GarageApp>
			<BankingApp v-if="isAppActive('Banking')"></BankingApp>
			<WhatsappApp v-if="isAppActive('Whatsapp')"></WhatsappApp>
			<iMessageApp v-if="isAppActive('iMessage')"></iMessageApp>
			<ProfileApp v-if="isAppActive('profile')"></ProfileApp>
			<CallApp v-if="isAppActive('call')"></CallApp>
		</IPhone>
	</div>
</template>

<script>
import IPhone from "./components/IPhone.vue";

import HomeApp from "./components/apps/Home.vue";
import RadioApp from "./components/apps/radio/RadioApp.vue";
import GarageApp from "./components/apps/garage/GarageApp.vue";
import BankingApp from "./components/apps/banking/BankingApp.vue";
import WhatsappApp from "./components/apps/whatsapp/WhatsappApp.vue";
import iMessageApp from "./components/apps/imessage/iMessageApp.vue";
import CallApp from "./components/apps/call/CallApp.vue";
import ProfileApp from "./components/apps/profile/ProfileApp.vue";

export default {
	name: "App",

	components: {
		IPhone,
		HomeApp,
		RadioApp,
		GarageApp,
		BankingApp,
		WhatsappApp,
		iMessageApp,
		CallApp,
    ProfileApp,
	},

	data: function () {
		return {
			activeAppName: "whatsapp",
		};
	},

	methods: {
		isAppActive: function (appName) {
			return appName.toLowerCase() === this.activeAppName.toLowerCase();
		},
		onAppClick: function (appName) {
			this.activeAppName = appName;
		},
	},
};
</script>

<style lang="scss">
</style>
