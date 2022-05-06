<template>
	<div class="tweet-post-form">
		<div class="tweet-post-form__header">
			<div class="tweet-post-form__header-section">
				<img class="tweet-post-form__icon" src="@/assets/img/icons/post.png" />
				<div class="tweet-post-form__header-text">
					<p class="tweet-post-form__title">Type your message here</p>
					<p class="tweet-post-form__subtitle">150 symbols</p>
				</div>
			</div>
			<img class="tweet-post-form__close-button" src="@/assets/img/icons/twitter-form-close.svg" @click="onCloseButtonClick" />
		</div>
		<textarea class="tweet-post-form__input" v-model="inputValue" />
		<Button theme="banking" @click.native="onPostSubmitButtonClick">Send It</Button>
	</div>
</template>

<script>
import Button from "../../Button.vue";
export default {
	components: { Button },
	data: function () {
		return {
			inputValue: "",
		};
	},
	props: {
		onPostSubmit: Function,
		onCloseButtonClick: Function,
	}, 
  methods: {
    onPostSubmitButtonClick: function() {
      this.onPostSubmit(inputValue);
    }
  }
};
</script>

<style lang="scss">
.tweet-post-form {
	display: flex;
	flex-direction: column;
	align-items: center;
	gap: 1vw;

	padding: 0.3vw 0.5vw;

	background-color: #fcfcfc;
	border-radius: 1.5vw 1.5vw 0 0;

	&__header {
		display: flex;
		justify-content: space-between;

		width: 100%;
	}

	&__header-section {
		display: flex;
		align-items: center;
		gap: 0.25vw;
	}

	&__icon {
		height: 2vw;
	}
	&__title {
		color: black;

		font-size: 0.9vw;
		font-weight: 700;
	}
	&__subtitle {
		color: #87898d;

		font-size: 0.7vw;
		font-weight: 500;
	}
	&__close-button {
		align-self: flex-start;
		flex-shrink: 0;
		width: 1vw;
	}

	&__input {
		width: 100%;
		height: 5vw;

		box-sizing: border-box;
		padding: 0.5vw 0.75vw;

		font-size: 0.85vw;

		background-color: white;

		border: none;
		border-radius: 1vw;
		outline: none;

		resize: none;
	}
}
</style>