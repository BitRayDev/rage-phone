<template>
	<div class="whatsapp-chat-screen">
		<div class="whatsapp-app__chat-info whatsapp-chat-info">
			<img class="whatsapp-chat-info__icon" :src="chat.icon" />
			<div class="whatsapp-chat-info__text">
				<p class="whatsapp-chat-info__name purple-gradient-text">{{chat.name}}</p>
				<p
					:class="`whatsapp-chat-info__status ${chat.status === 'online' ? 'whatsapp-chat-info__status_online' : ''}`"
				>{{chat.status}}</p>
			</div>
		</div>
		<hr class="whatsapp-app__splitter" />
		<div class="whatsapp-app__chat">
			<div
				:class="`whatsapp-app__message whatsapp-message whatsapp-message_type_${message.type}`"
				v-for="message in chat.messages"
			>
				<p class="whatsapp-message__text">{{message.text}}</p>
				<p class="whatsapp-message__time">{{message.time}}</p>
			</div>
		</div>
    <input class="whatsapp-app__respond-input" type="text" placeholder="Respond..." @input="onInputValueChange">
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
.whatsapp-chat-info {
	display: flex;
	align-items: center;
	gap: 0.3vw;

	&__icon {
		width: 2.5vw;
	}

	&__name {
		font-size: 1vw;
		font-weight: 700;
	}
	&__status {
		font-size: 0.9vw;
		font-weight: 600;
		text-transform: capitalize;

		&_online {
			color: #3bd738;
		}
	}
}

.whatsapp-message {
	display: flex;
	flex-direction: column;
	gap: 0.2vw;

	&__text {
		width: 8vw;

		padding: 1vw;

		font-size: 0.7vw;
		font-weight: 500;
	}

	&__time {
		font-size: 0.7vw;
	}

	&_type {
		&_incoming {
			align-self: flex-start;

			& > .whatsapp-message__text {
				background: linear-gradient(
					90.77deg,
					rgba(62, 59, 94, 0.54) -2.33%,
					rgba(62, 59, 94, 0) 114.47%
				);

				border-radius: 0 0.5vw 0.5vw 0.5vw;
			}
		}

		&_outcoming {
			align-self: flex-end;

			& > .whatsapp-message__text {
				background: linear-gradient(
					-90.77deg,
					rgba(62, 59, 94, 0.54) -2.33%,
					rgba(62, 59, 94, 0) 114.47%
				);

				border-radius: 0.5vw 0 0.5vw 0.5vw;
			}

			& > .whatsapp-message__time {
				text-align: right;
			}
		}
	}
}

.whatsapp-app__chat {
	display: flex;
	flex-direction: column;
	gap: 0.25vw;

	padding-right: 0.5vw;

	overflow: auto;
}

.whatsapp-chat-screen {
	display: flex;
	flex-direction: column;
	gap: 0.25vw;

	overflow: hidden;
}
</style>