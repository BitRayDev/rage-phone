<template>
	<div class="market-post-form">
		<textarea
			class="market-post-form__input"
			placeholder="Description for market thing leave here"
			v-model="inputValue"
		/>
		<div class="market-post-form__tags">
			<p
				class="market-post-form__tag"
				v-for="tag in availableTags"
				:style="{borderColor: tag.color, color: tag === selectedTag ? 'white' : tag.color, backgroundColor: tag === selectedTag ? tag.color : 'transparent'}"
				@click="() => selectTag(tag)"
			>{{tag.text}}</p>
		</div>

		<div class="market-post-form__buttons">
			<Button theme="banking" @click.native="onSubmitButtonClick">Send It</Button>
			<Button theme="banking" @click.native="onCancel">Go Back</Button>
		</div>
	</div>
</template>

<script>
import Button from "../../Button.vue";
export default {
	components: { Button },
	data: function () {
		return {
			inputValue: "",
			selectedTag: {},
			availableTags: [
				{
					text: "Buy",
					color: "#3BD738",
				},
				{
					text: "Sell",
					color: "#FF4646",
				},
			],
		};
	},
	props: {
		onSubmit: Function,
		onCancel: Function,
	},
	methods: {
		onSubmitButtonClick: function () {
			this.onPostSubmit(inputValue);
		},
		selectTag: function (tag) {
			this.selectedTag = tag;
		},
	},
};
</script>

<style lang="scss">
.market-post-form {
	display: flex;
	flex-direction: column;
	align-items: center;
	gap: .5vw;

	height: 100%;

	padding: 0.3vw 0.5vw;

	border-radius: 1.5vw 1.5vw 0 0;

	&__input {
		flex-grow: 1;

		width: 100%;

		box-sizing: border-box;
		padding: 0.5vw 0.75vw;

		font-size: 0.85vw;

		background-color: white;

		border: none;
		border-radius: 1vw;
		outline: none;

		resize: none;
	}

	&__tags {
		display: flex;
		align-items: center;
		gap: 0.5vw;
	}

	&__tag {
		padding: 0.4vw 0.8vw;

		font-size: .8vw;
		font-weight: 500;

		border: 0.1vw solid;
		border-radius: 100vw;
	}

  &__buttons {
    display: flex;
    flex-direction: column;
    gap: .25vw;

    width: 100%;
  }
}
</style>