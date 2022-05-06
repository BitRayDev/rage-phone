<template>
	<div class="appstore-list">
		<div class="appstore-list__app appstore-app" v-for="app in apps">
			<img class="appstore-app__icon" :src="app.icon" />
			<div class="appstore-app__body">
				<div class="appstore-app__header">
					<p class="appstore-app__title">{{app.title}}</p>
					<p class="appstore-app__downloads">{{app.downloads}}</p>
				</div>
				<p class="appstore-app__description">{{app.description}}</p>
				<Button class="appstore-app__button" theme="banking">Install</Button>
			</div>
		</div>
	</div>
</template>

<script>
import Button from "../../Button.vue";

export default {
	components: { Button },
	props: {
		apps: Array,
	},
};
</script>

<style lang="scss">
.appstore-app {
	display: flex;
	align-items: flex-start;
	gap: 0.6vw;

	padding: 0.4vw 0.5vw;

	background-color: white;
	border-radius: 0.5vw;

	transition: filter 100ms ease-out;
	&:hover {
		filter: drop-shadow(0 0 0.5vw rgba(187, 187, 187, 0.5));
	}

	&__icon {
		flex-shrink: 0;

		width: 2.5vw;

		border-radius: 0.25vw;
	}

	&__body {
		display: flex;
		flex-direction: column;
		gap: 0.1vw;
		flex-grow: 1;
	}

	&__header {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	&__title {
		color: #200e32;

		font-size: 0.9vw;
		font-weight: 600;
	}
	&__downloads {
		color: #8c8098;

		font-size: 0.7vw;
		font-weight: 500;
	}

	&__description {
		width: 9vw;

		font-size: 0.75vw;
		font-weight: 500;

		color: #200e32;

		overflow: hidden;
	}

	&__button {
		width: fit-content;

		padding: 0.25vw 0.4vw;

		font-size: 0.75vw;
	}
}

.appstore-list {
	display: flex;
	flex-direction: column;
	flex-grow: 1;
	gap: 0.4vw;

	padding-right: 0.5vw;

	overflow: auto;
}
</style>