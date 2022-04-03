<template>
	<div class="app radio-app">
		<div class="radio-app__dashboard">
			<div class="radio-app__info">
				<p class="radio-app__current-frequency">{{currentStation.frequency}}</p>
				<p class="radio-app__current-station-name">{{currentStation.name}}</p>
				<p class="radio-app__current-track-name">{{currentTrackName}}</p>
			</div>
			<div class="radio-app__controls">
				<div class="radio-app__play-button" @click="onPlayButtonClicked">
					<img
						class="radio-app__play-button-icon"
						:src="isPlaying ? require('../../../assets/img/icons/stop.svg') : require('../../../assets/img/icons/play.svg')"
					/>
				</div>
			</div>
		</div>
		<div class="radio-app__stations-list">
			<div class="radio-app__station" v-for="station in stations" :key="station">
				<p class="radio-app__station-name">{{station.name}}</p>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data: function () {
		return {
			currentStation: {
				frequency: "90,8",
				name: "BEST FM",
			},
			currentTrackName: "Best FM 90.8 - Skpje, m",

			isPlaying: false,

			stations: [
				{
					frequency: "90,8",
					name: "Hit Radio",
				},
				{
					frequency: "90,8",
					name: "Hit Radio",
				},
				{
					frequency: "90,8",
					name: "Hit Radio",
				},
				{
					frequency: "90,8",
					name: "Hit Radio",
				},
				{
					frequency: "90,8",
					name: "Hit Radio",
				},
				{
					frequency: "90,8",
					name: "Hit Radio",
				},
			],
		};
	},
  methods: {
    onPlayButtonClicked: function () {
      this.isPlaying = !this.isPlaying;
    }
  }
};
</script>

<style lang="scss">
.radio-app {
  display: flex;
  flex-direction: column;

	height: 100%;

	background: url("../../../assets/img/backgrounds/beige.svg");
  background-size: 100% 100%;

  overflow: hidden;

	&__dashboard {
	}

	&__info {
		padding: 2.5vw 0.5vw;
		padding-bottom: 2vw;

		text-align: center;
	}
	&__current-frequency {
		font-size: 4vw;
		font-weight: 300;
		line-height: 1;
	}
	&__current-station-name {
		font-size: 1vw;
		font-weight: 600;

		color: #5e1f2e;
	}
	&__current-track-name {
		font-size: 1vw;
	}

	&__controls {
		display: flex;
		align-items: center;
		justify-content: center;

		padding: 1.25vw;

		background: url("../../../assets/img/audio-spectro.svg");
		background-size: 100% 100%;
		background-repeat: no-repeat;
	}
	&__play-button {
		display: flex;
		align-items: center;
		justify-content: center;

		width: 2.5vw;
		height: 2.5vw;

		background-color: #965163;

		border: 0.2vw solid white;
		border-radius: 100vw;

		filter: drop-shadow(0 0 0.25vw rgba(0, 0, 0, 0.5));

    transition: filter 150ms ease-out;
		&:hover {
      filter: drop-shadow(0 0 0.25vw rgba(255, 255, 255, 0.5));
		}
	}
	&__play-button-icon {
		width: 0.8vw;
	}

	&__stations-list {
		overflow: auto;
    
    flex-grow: 1;

		&::-webkit-scrollbar {
			width: 0.25vw;
		}
		&::-webkit-scrollbar-track {
			background-color: #613741;
		}
		&::-webkit-scrollbar-thumb {
			background-color: #9b5465;
		}
	}
	&__station {
		padding: 1vw;

		background-color: #7b4354;

		&:nth-child(2n) {
			background-color: #743f4f;
		}
	}
	&__station-name {
		font-size: 1vw;
		font-weight: 600;
	}
}
</style>