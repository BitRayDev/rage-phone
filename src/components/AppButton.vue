<template>
	<div class="app-button">
		<img class="app-button__icon" :src="icon" />
		<p class="app-button__label" v-if="label">{{label}}</p>
	</div>
</template>

<script>
export default {
	props: {
		label: {
			type: String,
			required: false,
		},
		icon: String
	},
};
</script>

<style lang="scss">
.app-button {
	display: flex;
	flex-direction: column;
	align-items: center;
	gap: 0.2vw;

	width: 3vw;

	cursor: pointer;

	&__icon {
		width: 100%;

    transition: filter 200ms ease-out;
		&:hover {
			filter: drop-shadow(0 0 1vw rgba(255, 255, 255, 0.25));
		}
	}

	&__label {
		font-size: 0.6vw;
		font-weight: 700;

		text-transform: uppercase;
	}
}
</style>