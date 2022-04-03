<template>
	<div class="whatsapp-chats-screen">
		<div class="whatsapp-app__section">
			<p class="whatsapp-app__section-title">Chats</p>
			<hr class="whatsapp-app__splitter" />
		</div>
		<div class="whatsapp-app__chats">
			<div class="whatsapp-app__chat-preview whatsapp-chat-preview" v-for="chat in chats" @click="() => onChatClick(chat)">
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
</template>

<script>
export default {
	props: {
		chats: Array,
		onChatClick: Function,
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
		font-size: .9vw;
		font-weight: 700;
	}

	&__time {
		font-size: 0.7vw;
		font-weight: 500;

		opacity: 0.35;
	}

	&__recent-message {
		width: 9vw;

		font-size: 0.75vw;
		font-weight: 600;

		opacity: 0.25;

		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}
}

.whatsapp-chats-screen {
  display: flex;
  flex-direction: column;
  gap: .5vw;

  overflow: hidden;
}
</style>