<template>
	<div :class="`search-input search-input_theme_${theme}`">
		<img class="search-input__icon" src="@/assets/img/icons/search.svg" />
		<input type="text" :placeholder="placeholder" class="search-input__input" @input="onValueChange" />
	</div>
</template>

<script>
export default {
	props: {
		onValueChange: Function,
		placeholder: String,
		theme: String,
	},
};
</script>

<style lang="scss">
.search-input {
	display: flex;
	gap: 0.4vw;

	padding: 0.5vw 0.75vw;

	background-color: #0b0a16;

	border-radius: 0.5vw;

	&__icon {
		width: 0.9vw;
	}

	&__input {
		flex-grow: 1;

		font-size: 0.8vw;
		font-weight: 500;

		color: white;
		background: none;

		border: none;
		outline: none;

		&::placeholder {
			font-weight: 400;

			color: #8c8198;
		}
	}

	&_theme {
		&_light {
			background-color: #ffffff;

      & > .search-input__input {
        color: #200E32;
      }
		}
		&_dark {
			background-color: #0b0a16;

      & > .search-input__input {
        color: white;
      }
		}
	}
}
</style>