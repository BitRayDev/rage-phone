<template>
	<div class="whatsapp-app app">
		<p class="whatsapp-app__title">WHAT'S APP</p>
		<WhatsappChatsList :chats="chats" :onChatClick="onChatClick" v-if="!currentChat"></WhatsappChatsList>
		<WhatsappChat :chat="currentChat" v-if="currentChat"></WhatsappChat>
	</div>
</template>

<script>
import avatar from "../../../assets/img/avatar.png";
import WhatsappChat from "./WhatsappChat.vue";
import WhatsappChatsList from "./WhatsappChatsList.vue";

export default {
	components: { WhatsappChatsList, WhatsappChat },
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
.whatsapp-app {
	display: flex;
	flex-direction: column;
	gap: 0.4vw;

	background: url("../../../assets/img/backgrounds/purple.svg");
	background-size: 100% 100%;

	padding: 0.5vw;
	padding-top: 2vw;

	overflow: hidden;

	*::-webkit-scrollbar {
		width: 0.2vw;
	}
	*::-webkit-scrollbar-track {
		background: #522644;
	}
	*::-webkit-scrollbar-thumb {
		background: #e33ee6;
	}

	&__title {
		font-size: 1.5vw;
		font-weight: 700;

		line-height: 1;
	}

	&__section-title {
		opacity: 0.55;

		font-size: 0.7vw;
		font-weight: 600;
	}

	&__splitter {
		opacity: 0.05;
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
    background: none;
    border: none;
    outline: none;

    padding: .25vw .5vw;

    color: white;
    font-size: .7vw;
    font-weight: 500;

    border: .1vw solid rgba(255, 255, 255, .08);
    border-radius: 100vw;

    &::placeholder {
      opacity: .35;
    }
  }
}
</style>