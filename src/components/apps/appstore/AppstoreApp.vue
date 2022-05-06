<template>
	<div class="appstore app">
		<p class="appstore__title">Appstore</p>
		<AppstoreList :apps="apps"></AppstoreList>
	</div>
</template>

<script>
import avatar from "../../../assets/img/avatar1.png";

import AppstoreList from "./AppstoreList.vue";
import Button from "../../Button.vue";

export default {
	components: { AppstoreList },
	data: function () {
		return {
			apps: [
				{
					icon: avatar,
          title: "Fortnite",
					downloads: "12k downloads",
					description: "Description for this app should be here",
				},
			],
		};
	},
	methods: {
		onInstallButtonClick: function () {
			// TODO: Add handler
		}
	},
};
</script>

<style lang="scss">
.appstore {
	display: flex;
	flex-direction: column;
	gap: 0.4vw;

	background: #f1f1f1;
	background-size: 100% 100%;

	padding: 0.5vw;
	padding-top: 2vw;

	overflow: hidden;

	*::-webkit-scrollbar {
		width: 0.2vw;
	}
	*::-webkit-scrollbar-track {
		background: #e9e9e9;
	}
	*::-webkit-scrollbar-thumb {
		background: #b3b3b3;
	}

	&__title {
		color: #200e32;

		font-size: 1.5vw;
		font-weight: 700;

		line-height: 1;
	}

	&__apps {
	}
}
</style>