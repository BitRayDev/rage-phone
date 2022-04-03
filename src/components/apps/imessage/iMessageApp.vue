<template>
	<div class="imessage-app app">
		<p class="imessage-app__title">iMessage</p>
		<iMessageChatsList :chats="chats" :onChatClick="onChatClick" v-if="!currentChat"></iMessageChatsList>
		<iMessageChat :chat="currentChat" v-if="currentChat"></iMessageChat>
	</div>
</template>

<script>
import avatar from "../../../assets/img/avatar1.png";

import IMessageChat from "./iMessageChat.vue";
import IMessageChatsList from "./iMessageChatsList.vue";

export default {
	components: { IMessageChatsList, IMessageChat },
	data: function () {
		return {
			chats: [
				{
					icon: avatar,
					name: "Romario Richardson",
					status: "online",
					messages: [
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
					],
				},
				{
					icon: avatar,
					name: "Romario Richardson",
					status: "online",
					messages: [
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
					],
				},
				{
					icon: avatar,
					name: "Romario Richardson",
					status: "online",
					messages: [
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
					],
				},
				{
					icon: avatar,
					name: "Romario Richardson",
					status: "online",
					messages: [
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
					],
				},
				{
					icon: avatar,
					name: "Romario Richardson",
					status: "online",
					messages: [
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
					],
				},
				{
					icon: avatar,
					name: "Romario Richardson",
					status: "online",
					messages: [
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
					],
				},
				{
					icon: avatar,
					name: "Romario Richardson",
					status: "online",
					messages: [
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
					],
				},
				{
					icon: avatar,
					name: "Romario Richardson",
					status: "online",
					messages: [
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
					],
				},
				{
					icon: avatar,
					name: "Romario Richardson",
					status: "online",
					messages: [
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
					],
				},
				{
					icon: avatar,
					name: "Romario Richardson",
					status: "online",
					messages: [
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
					],
				},
				{
					icon: avatar,
					name: "Romario Richardson",
					status: "online",
					messages: [
						{
							type: "incoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
						{
							type: "outcoming",
							text: "Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!! Sheees! Bro, we did it!! Come on! WAKE UP!!!",
							time: "0:51",
							status: "",
						},
					],
				},
			],
			currentChat: null,
		};
	},
	methods: {
		onChatClick: function (chat) {
			this.currentChat = chat;
		},
	},
};
</script>

<style lang="scss">
.imessage-app {
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

	&__section-title {
		color: #200e32;

		opacity: 0.55;

		font-size: 0.7vw;
		font-weight: 600;
	}

	&__splitter {
		color: #200e32;

		opacity: 0.25;
	}

	&__chats {
		display: flex;
		flex-direction: column;
		flex-grow: 1;
		gap: 0.4vw;

		padding-right: 0.5vw;

		overflow: auto;
	}

	&__chat {
	}

	&__respond-input {
		background: #eaeaea;
		border: none;
		outline: none;

		padding: 0.25vw 0.5vw;

		color: #200e32;

		font-size: 0.8vw;
		font-weight: 600;
		text-align: center;

		border: 0.1vw solid rgba(255, 255, 255, 0.08);
		border-radius: 0.25vw;

		&::placeholder {
			color: #8c8098;
		}
	}
}
</style>