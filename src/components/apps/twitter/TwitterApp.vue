<template>
	<div class="twitter-app app">
		<p class="twitter-app__title">Twitter</p>
		<TweetsList :tweets="tweets"></TweetsList>
		<TweetPostForm v-if="isPostFormActive" :onCloseButtonClick="onCloseFormButtonClick" :onPostSubmit="onPostSubmitButtonClick"></TweetPostForm>
		<div
			class="twitter-app__post-button twitter-post-button"
			v-if="!isPostFormActive"
			@click="onPostButtonClick"
		>
			<img class="twitter-post-button__icon" src="@/assets/img/icons/write-tweet.svg" />
		</div>
	</div>
</template>

<script>
import avatar from "../../../assets/img/avatar1.png";

import IMessageChat from "./TweetPostForm.vue";
import IMessageChatsList from "./TweetsList.vue";
import TweetsList from "./TweetsList.vue";

import testAvatar from "@/assets/img/avatar1.png";
import TweetPostForm from "./TweetPostForm.vue";

export default {
	components: { TweetsList, TweetPostForm },
	data: function () {
		return {
			isPostFormActive: false,
			tweets: [
				{
					icon: testAvatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "Will you guys rush it today? Tired to wait. . .",
					likes: 28,
					shares: 5,
					comments: 21,
				},
				{
					icon: testAvatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "Will you guys rush it today? Tired to wait. . .",
					likes: 28,
					shares: 5,
					comments: 21,
				},
				{
					icon: testAvatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "Will you guys rush it today? Tired to wait. . .",
					likes: 28,
					shares: 5,
					comments: 21,
				},
				{
					icon: testAvatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "Will you guys rush it today? Tired to wait. . .",
					likes: 28,
					shares: 5,
					comments: 21,
				},
				{
					icon: testAvatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "Will you guys rush it today? Tired to wait. . .",
					likes: 28,
					shares: 5,
					comments: 21,
				},
				{
					icon: testAvatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "Will you guys rush it today? Tired to wait. . .",
					likes: 28,
					shares: 5,
					comments: 21,
				},
				{
					icon: testAvatar,
					author: {
						name: "Richard",
						id: "@retard",
					},
					time: "12h",
					text: "Will you guys rush it today? Tired to wait. . .",
					likes: 28,
					shares: 5,
					comments: 21,
				},
			],
		};
	},
	methods: {
		onPostButtonClick: function () {
			this.isPostFormActive = true;
		},
		onCloseFormButtonClick: function () {
			this.isPostFormActive = false;
		},
    onPostSubmitButtonClick: function() {
      // TODO: Add handler
    }
	},
};
</script>

<style lang="scss">
.twitter-app {
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

	&__tweets {
	}

	&__post-button {
		position: absolute;
		right: 1vw;
		bottom: 1vw;
	}
}

.twitter-post-button {
	display: flex;
	align-items: center;
	justify-content: center;

	height: 3vw;
	width: 3vw;

	background-color: #4c9eeb;
	border-radius: 100vw;

	transition: box-shadow 100ms ease-out;
	&:hover {
		box-shadow: 0px 0.1vw 0.5vw rgba(0, 0, 0, 0.25);
	}

	&__icon {
		height: 40%;
	}
}
</style>