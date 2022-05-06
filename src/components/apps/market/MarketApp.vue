<template>
	<div class="market-app app">
		<p class="market-app__title">Market</p>
		<MarketPostForm
			:onCancel="onCancel"
			:onSubmit="onSubmit"
			v-if="isPostFormActive"
		></MarketPostForm>
		<template v-if="!isPostFormActive">
		  <MarketAdsList :ads="ads"></MarketAdsList>
  		<Button @click.native="onPostButtonClick" theme="banking">Sell my thing</Button>
		</template>
	</div>
</template>

<script>
import avatar from "../../../assets/img/avatar1.png";

import MarketAdsList from "./MarketAdsList.vue";
import MarketPostForm from "./MarketPostForm.vue";
import Button from "../../Button.vue";

export default {
	components: { MarketAdsList, MarketPostForm, Button },
	data: function () {
		return {
			isPostFormActive: false,
			ads: [
				{
					icon: avatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "i will buy AK-47 with armory bullets today, high price! Phone: 225 222 222",
					tags: [
						{
							text: "Buying",
							color: "#3BD738",
						},
					],
				},
				{
					icon: avatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "i will buy AK-47 with armory bullets today, high price! Phone: 225 222 222",
					tags: [
						{
							text: "Buying",
							color: "#3BD738",
						},
					],
				},
				{
					icon: avatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "i will buy AK-47 with armory bullets today, high price! Phone: 225 222 222",
					tags: [
						{
							text: "Buying",
							color: "#3BD738",
						},
					],
				},
				{
					icon: avatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "i will buy AK-47 with armory bullets today, high price! Phone: 225 222 222",
					tags: [
						{
							text: "Buying",
							color: "#3BD738",
						},
					],
				},
				{
					icon: avatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "i will buy AK-47 with armory bullets today, high price! Phone: 225 222 222",
					tags: [
						{
							text: "Buying",
							color: "#3BD738",
						},
					],
				},
				{
					icon: avatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "i will buy AK-47 with armory bullets today, high price! Phone: 225 222 222",
					tags: [
						{
							text: "Buying",
							color: "#3BD738",
						},
					],
				},
			],
		};
	},
	methods: {
		onPostButtonClick: function () {
			this.isPostFormActive = true;
		},
    onSubmit: function() {
      // TODO: Add handler
    },
		onCancel: function () {
			this.isPostFormActive = false;
		},
	},
};
</script>

<style lang="scss">
.market-app {
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

	&__ads {
	}
}
</style>