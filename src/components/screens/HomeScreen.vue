<template>
	<div class="home-screen screen">
		<div class="home-screen__notification-widget notification-widget" v-if="notification">
			<img class="notification-widget__icon" :src="notification.icon" />
			<div class="notification-widget__text-container">
				<div class="notification-widget__header">
					<p class="notification-widget__title">{{notification.title}}</p>
					<p class="notification-widget__time">{{notification.time}}</p>
				</div>
				<p class="notification-widget__text">{{notification.text}}</p>
			</div>
		</div>
		<div class="home-screen__apps">
			<AppButton v-for="(app, index) in apps" :key="index" :icon="app.icon" :label="app.label" :onClick="() => onAppClick(app.label)"></AppButton>
		</div>
		<div class="home-screen__hotbar">
			<div class="home-screen__hotbar-apps">
				<AppButton v-for="(app, index) in hotbarApps" :key="index" :icon="app.icon"></AppButton>
			</div>
		</div>
	</div>
</template>

<script>
import AppButton from "../AppButton.vue";

export default {
	components: { AppButton },
	props: {
		notification: Object,
		apps: Array,
		hotbarApps: Array,
    onAppClick: Function
	},
};
</script>

<style lang="scss">
.notification-widget {
	display: flex;
	gap: 0.5vw;

  padding: .3vw .5vw;

	background-color: rgba(255, 255, 255, 0.8);
	border-radius: 0.8vw;

	&__icon {
		width: 2vw;
	}

	&__text-container {
	}
	&__header {
		display: flex;
	}
	&__title {
    flex-grow: 1;

		font-size: 0.8vw;
		font-weight: 600;

		color: #222222;
	}
	&__time {
		font-size: 0.6vw;
		font-weight: 500;
    white-space: nowrap;

		color: #3f3f3f;
		opacity: 0.5;
	}
	&__text {
		font-size: 0.8vw;
		font-weight: 500;

		color: #3f3f3f;
	}
}

.home-screen {
	position: relative;
	width: 100%;
	height: 100%;

	box-sizing: border-box;

	padding: 0.5vw;
	padding-top: 1.5vw;

	background: url("../../assets/img/test-bg.png");
	background-size: cover;

	&__notification-widget {
    margin-bottom: .75vw;
	}

	&__apps {
		display: flex;
		flex-wrap: wrap;
		gap: 0.6vw;
	}

	&__hotbar {
		position: absolute;
		bottom: 0.75vw;

		width: 87%;
		left: 50%;
		transform: translateX(-50%);

		padding: 0.4vw 0.5vw;

		background: rgba(255, 255, 255, 0.07);

		border-radius: 0.7vw;

		backdrop-filter: blur(1.2vw);
	}

	&__hotbar-apps {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
}
</style>