<template>
	<div class="tweets-list">
		<div class="tweets-list__tweet tweet" v-for="tweet in tweets">
			<img class="tweet__icon" :src="tweet.icon" />
			<div class="tweet__body">
				<div class="tweet__header">
					<p class="tweet__author-name">{{tweet.author.name}}</p>
					<div class="tweet__header-section">
						<p class="tweet__author-id">{{tweet.author.id}}</p>
						<p class="tweet__time">{{tweet.time}}</p>
					</div>
				</div>
				<p class="tweet__text">{{tweet.text}}</p>
				<div class="tweet__stats">
					<div class="tweet__stats-section">
						<img class="tweet__stats-icon" src="@/assets/img/icons/like.svg" />
						<p class="tweet__stats-value">{{tweet.likes}}</p>
					</div>
					<div class="tweet__stats-section">
						<img class="tweet__stats-icon" src="@/assets/img/icons/share.svg" />
						<p class="tweet__stats-value">{{tweet.shares}}</p>
					</div>
					<div class="tweet__stats-section">
						<img class="tweet__stats-icon" src="@/assets/img/icons/comment.svg" />
						<p class="tweet__stats-value">{{tweet.comments}}</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		tweets: Array,
	},
};
</script>

<style lang="scss">
.tweet {
	display: flex;
	align-items: center;
	gap: 0.6vw;

	padding: 0.4vw 0.5vw;

	border-radius: 0.3vw;

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
    gap: .1vw;
		flex-grow: 1;
	}

	&__header {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	&__header-section {
		display: flex;
		align-items: center;
		gap: 0.25vw;
	}

	&__author-name {
		color: #200e32;

		font-size: 0.9vw;
		font-weight: 600;
	}
	&__author-id {
		color: #8c8098;

		font-size: 0.7vw;
		font-weight: 500;
	}
	&__time {
		color: #8c8098;

		font-size: 0.7vw;
		font-weight: 500;
	}

	&__text {
		width: 9vw;
		max-height: 1.6vw;

		font-size: 0.75vw;
		font-weight: 500;

		color: #200e32;

		overflow: hidden;
	}

	&__stats {
		display: flex;
		align-items: center;
		gap: 0.5vw;
	}

	&__stats-section {
		display: flex;
		align-items: center;
		gap: 0.25vw;
	}

  &__stats-icon {
    height: .65vw;
  }
	&__stats-value {
		color: #687684;
		font-size: 0.8vw;
	}
}

.tweets-list {
	display: flex;
	flex-direction: column;
	flex-grow: 1;
	gap: 0.4vw;

	padding-right: 0.5vw;

	overflow: auto;
}
</style>