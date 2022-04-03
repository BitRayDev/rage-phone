<template>
	<div class="imessage-chat-screen">
		<div class="imessage-app__chat-info imessage-chat-info">
			<img class="imessage-chat-info__icon" :src="chat.icon" />
			<p class="imessage-chat-info__chat-with">Chat with</p>
			<p class="imessage-chat-info__name">{{chat.name}}</p>
		</div>
		<hr class="imessage-app__splitter" />
		<div class="imessage-app__chat">
			<div
				:class="`imessage-app__message imessage-message imessage-message_type_${message.type}`"
				v-for="message in chat.messages"
			>
				<p class="imessage-message__text">{{message.text}}</p>
				<p class="imessage-message__time">{{message.time}}</p>
			</div>
		</div>
		<input
			class="imessage-app__respond-input"
			type="text"
			placeholder="Respond..."
			@input="onInputValueChange"
		/>
	</div>
</template>

<script>
export default {
	props: {
		chat: Object,
		onInputValueChange: Function,
	},
};
</script>

<style lang="scss">
.imessage-chat-info {
	display: flex;
	flex-direction: column;
	align-items: center;
	gap: 0.1vw;

	&__icon {
		width: 3.5vw;

		border-radius: 100vw;
	}

  &__chat-with {
    color: #200E32;
    opacity: 0.55;

		font-size: .7vw;
		font-weight: 600;
	}

	&__name {
    color: #200E32;

		font-size: .9vw;
		font-weight: 700;
	}
}

.imessage-message {
	display: flex;
	justify-content: space-between;
	gap: 0.2vw;

	width: 10vw;

	padding: 1vw;

	background: white;

	&__text {
		width: 9vw;

		color: #200e32;

		font-size: 0.7vw;
		font-weight: 500;
	}

	&__time {
		color: #8c8098;

		font-size: 0.7vw;
	}

	&_type {
		&_incoming {
			align-self: flex-start;

			border-radius: 0 0.5vw 0.5vw 0.5vw;
		}

		&_outcoming {
			align-self: flex-end;

			border-radius: 0.5vw 0 0.5vw 0.5vw;
		}
	}
}

.imessage-app__chat {
	display: flex;
	flex-direction: column;
	gap: 0.25vw;

	padding-right: 0.5vw;

	overflow: auto;
}

.imessage-chat-screen {
	display: flex;
	flex-direction: column;
	gap: 0.25vw;

	overflow: hidden;
}
</style>