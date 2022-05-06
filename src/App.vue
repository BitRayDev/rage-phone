<template>
	<div id="app">
		<IPhone @go-back="onAppClick('home')" :bottom-line-color="getBottomLineColor" :status-bar-theme="getStatusBarTheme">
			<HomeApp :onAppClick="onAppClick" v-if="isAppActive('Home')"></HomeApp>
			<RadioApp v-if="isAppActive('Radio')"></RadioApp>
			<GarageApp v-if="isAppActive('Garage')"></GarageApp>
			<BankingApp v-if="isAppActive('Banking')"></BankingApp>
			<WhatsappApp v-if="isAppActive('Whatsapp')"></WhatsappApp>
			<iMessageApp v-if="isAppActive('iMessage')"></iMessageApp>
			<ProfileApp v-if="isAppActive('profile')"></ProfileApp>
			<CallApp v-if="isAppActive('call')"></CallApp>
      <TwitterApp v-if="isAppActive('twitter')"></TwitterApp>
      <Instagram v-if="isAppActive('instagram')"></Instagram>
      <MarketApp v-if="isAppActive('market')"></MarketApp>
      <AppstoreApp v-if="isAppActive('appstore')"></AppstoreApp>
      <FlashlightApp v-if="isAppActive('flashlight')"></FlashlightApp>
      <SettingsApp v-if="isAppActive('settings')"></SettingsApp>
      <CalculatorApp v-if="isAppActive('calculator')"></CalculatorApp>
      <LifeInvaderApp v-if="isAppActive('life-invader')"></LifeInvaderApp>
      <FractionApp v-if="isAppActive('fraction')"></FractionApp>
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
import TwitterApp from "./components/apps/twitter/TwitterApp.vue";
import MarketApp from "./components/apps/market/MarketApp.vue";
import AppstoreApp from "./components/apps/appstore/AppstoreApp.vue";
import FlashlightApp from "./components/apps/flashlight/FlashlightApp.vue";
import SettingsApp from "./components/apps/settings/SettingsApp";
import CalculatorApp from "./components/apps/calculator/CalculatorApp";
import LifeInvaderApp from "./components/apps/life-invader/LiveInvaderApp";
import FractionApp from "./components/apps/fraction/FractionApp";

export default {
	name: "App",

	components: {
    FractionApp,
    LifeInvaderApp,
    CalculatorApp,
    SettingsApp,
		IPhone,
		HomeApp,
		RadioApp,
		GarageApp,
		BankingApp,
		WhatsappApp,
		iMessageApp,
		CallApp,
    ProfileApp,
    TwitterApp,
    MarketApp,
    AppstoreApp,
    FlashlightApp,
	},

	data: function () {
		return {
			activeAppName: "fraction",
		};
	},
  computed: {
    getBottomLineColor: function () {
      if(this.isAppActive('banking')) {
        return "black"
      }  else {
        return "white"
      }
    },
    getStatusBarTheme: function () {
      if(this.isAppActive('banking')) {
        return "black"
      }  else {
        return "white"
      }
    }
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
