<template>
	<div class="whatsapp-screen screen">
		<p class="whatsapp-screen__title">WHAT'S APP</p>
		<div class="whatsapp-screen__section">
			<div class="whatsapp-screen__section-header section-header">
				<p class="section-header__title">Chats</p>
				<hr class="section-header__splitter" />
			</div>
			<div class="whatsapp-screen__chats">
				<div class="whatsapp-screen__chat whatsapp-chat-preview" v-for="chat in chats">
					<div
						:class="`whatsapp-chat-preview__icon-container ${chat.status === 'online' ? 'whatsapp-chat-preview__icon-container_online' : ''}`"
					>
						<img class="whatsapp-chat-preview__icon" :src="chat.icon" />
					</div>
					<div class="whatsapp-chat-preview__text">
						<div class="whatsapp-chat-preview__header">
							<p class="whatsapp-chat-preview__name purple-gradient-text">{{chat.name}}</p>
							<p class="whatsapp-chat-preview__time">{{chat.messages[chat.messages.length-1].time}}</p>
						</div>
						<p class="whatsapp-chat-preview__recent-message">{{chat.messages[chat.messages.length-1].text}}</p>
					</div>
				</div>
			</div>
		</div>
    <div class="whatsapp-screen__section">
      <
    </div>
	</div>
</template>

<script>
import avatar from "../../assets/img/banking-screen/avatar.png";

export default {
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
			currentChat: {},
		};
	},
};
</script>

<style lang="scss">
.whatsapp-chat-preview {
	display: flex;
	align-items: center;
	gap: 0.6vw;

	transition: filter 100ms ease-out;
	&:hover {
		filter: drop-shadow(0 0 0.5vw rgba(73, 69, 124, 0.5));
	}

	&__icon-container {
		position: relative;

		&_online {
			&::before {
				content: "●";

				position: absolute;
				right: 0.25vw;
				bottom: -0.25vw;

				font-size: 1.2vw;

				color: #3bd738;

				filter: drop-shadow(0 0 0.2vw #000000);
			}
		}
	}

	&__icon {
		width: 2.5vw;

		flex-shrink: 0;
	}

	&__text {
		flex-grow: 1;

		height: 2vw;
	}

	&__header {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	&__name {
		font-size: 1vw;
		font-weight: 700;
	}

	&__time {
		font-size: 0.8vw;
		font-weight: 500;

		opacity: 0.35;
	}

	&__recent-message {
		width: 10vw;

		font-size: 0.8vw;
		font-weight: 600;

		opacity: 0.25;

		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}
}

.section-header {
	opacity: 0.55;
	font-size: 0.7vw;
	font-weight: 600;

	&__splitter {
		opacity: 0.05;
	}
}

.whatsapp-screen {
	display: flex;
	flex-direction: column;
	gap: 0.4vw;

	background: url("../../assets/img/garage-screen/background.svg");
	background-size: 100% 100%;

	padding: 0.5vw;
	padding-top: 2vw;

	overflow: hidden;

	&__title {
		font-size: 1.5vw;
		font-weight: 700;

		line-height: 1;
	}

	&__chats {
		display: flex;
		flex-direction: column;
		flex-grow: 1;
		gap: 0.4vw;

		padding-right: 0.25vw;

		overflow: auto;

		&::-webkit-scrollbar {
			width: 0.2vw;
		}
		&::-webkit-scrollbar-track {
			background: #522644;
		}
		&::-webkit-scrollbar-thumb {
			background: #e33ee6;
		}
	}

	&__chat {
	}
}
</style>