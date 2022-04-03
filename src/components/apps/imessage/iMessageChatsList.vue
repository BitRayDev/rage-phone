<template>
	<div class="imessage-chats-screen">
		<div class="imessage-app__section">
			<p class="imessage-app__section-title">Chats</p>
			<hr class="imessage-app__splitter" />
		</div>
		<div class="imessage-app__chats">
			<div class="imessage-app__chat-preview imessage-chat-preview" v-for="chat in chats" @click="() => onChatClick(chat)">
				<div
					:class="`imessage-chat-preview__icon-container ${chat.status === 'online' ? 'imessage-chat-preview__icon-container_online' : ''}`"
				>
					<img class="imessage-chat-preview__icon" :src="chat.icon" />
				</div>
				<div class="imessage-chat-preview__text">
					<div class="imessage-chat-preview__header">
						<p class="imessage-chat-preview__name">{{chat.name}}</p>
						<p class="imessage-chat-preview__time">{{chat.messages[chat.messages.length-1].time}}</p>
					</div>
					<p class="imessage-chat-preview__recent-message">{{chat.messages[chat.messages.length-1].text}}</p>
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
.imessage-chat-preview {
	display: flex;
	align-items: center;
	gap: 0.6vw;

  padding: .4vw .5vw;

  background: #FFFFFF;

  border-radius: .3vw;

	transition: filter 100ms ease-out;
	&:hover {
		filter: drop-shadow(0 0 0.5vw rgba(187, 187, 187, 0.5));
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
		flex-shrink: 0;

		width: 2.5vw;

    border-radius: .25vw;
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
    color: #200E32;

		font-size: .9vw;
		font-weight: 600;
	}

	&__time {
		color: #8C8098;

		font-size: 0.7vw;
		font-weight: 500;
	}

	&__recent-message {
		width: 9vw;

		font-size: 0.75vw;
		font-weight: 500;

    color: #200E32;

		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}
}

.imessage-chats-screen {
  display: flex;
  flex-direction: column;
  gap: .5vw;

  overflow: hidden;
}
</style>