<template>
	<button :class="`button button_theme_${theme}`">
		<slot />
	</button>
</template>

<script>
export default {
	props: {
		theme: {
			type: String,
			required: false,
		}
	},
};
</script>

<style lang="scss">
.button {
	width: 100%;

	padding: 0.5vw 0.75vw;

	color: black;
	background-color: white;

	border: none;
	border-radius: 0.25vw;

  transition: filter 100ms ease-out;
  &:hover {
    filter: drop-shadow(0 0 .25vw #FFFFFF22);
  }
}

@import "../assets/styles/button-themes/banking.scss";
@import "../assets/styles/button-themes/fraction.scss";
</style>