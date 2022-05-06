<template>
	<div class="ads-list">
		<div class="ads-list__ad ad" v-for="ad in ads">
			<img class="ad__icon" :src="ad.icon" />
			<div class="ad__body">
				<div class="ad__header">
					<p class="ad__author-name">{{ad.author.name}}</p>
					<div class="ad__header-section">
						<p class="ad__author-id">{{ad.author.id}}</p>
						<p class="ad__time">{{ad.time}}</p>
					</div>
				</div>
				<p class="ad__text">{{ad.text}}</p>
				<div class="ad__tags">
					<p class="ad__tag" v-for="tag in ad.tags" :style="{borderColor: tag.color, color: tag.color}">{{tag.text}}</p>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		ads: Array,
	},
};
</script>

<style lang="scss">
.ad {
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

		font-size: 0.75vw;
		font-weight: 500;

		color: #200e32;

		overflow: hidden;
	}

	&__tags {
		display: flex;
		align-items: center;
		gap: 0.5vw;
	}

  &__tag {
    padding: .25vw .5vw;

    font-size: .75vw;
    font-weight: 500;

    border: .1vw solid;
    border-radius: 100vw;
  }
}

.ads-list {
	display: flex;
	flex-direction: column;
	flex-grow: 1;
	gap: 0.4vw;

	padding-right: 0.5vw;

	overflow: auto;
}
</style>