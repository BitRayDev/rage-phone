<template>
	<div class="call-app app">
		<CallingScreen v-if="isActiveScreen('calling')"></CallingScreen>
		<ContactsScreen v-if="isActiveScreen('contacts')"></ContactsScreen>
		<CallKeyboardScreen v-if="isActiveScreen('keyboard')"></CallKeyboardScreen>
	</div>
</template>

<script>
import CallingScreen from "./CallingScreen.vue";
import ContactsScreen from "./ContactsScreen.vue";
import CallKeyboardScreen from "./CallKeyboardScreen.vue";
export default {
	components: {
		CallingScreen,
		ContactsScreen,
		CallKeyboardScreen,
	},

	data: function () {
		return {
			activeScreenName: "keyboard",
		};
	},

	methods: {
		isActiveScreen: function (screenName) {
			return screenName.toLowerCase() === this.activeScreenName.toLowerCase();
		},
	},
};
</script>

<style lang="scss">
</style>