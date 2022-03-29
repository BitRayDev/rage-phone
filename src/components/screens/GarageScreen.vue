<template>
	<div class="screen garage-screen">
		<div class="garage-screen__title">Garage</div>
		<div class="garage-screen__search garage-search">
			<img class="garage-search__icon" src="@/assets/img/icons/search.svg" />
			<input type="text" placeholder="Search by carname" class="garage-search__input" v-model="searchValue"/>
		</div>
		<div class="garage-screen__cars">
			<div class="garage-screen__car garage-car" v-for="car in cars" v-if="car.name.toLowerCase().includes(searchValue.toLowerCase())">
				<img class="garage-car__icon" src="@/assets/img/garage-screen/car-icon.svg" />
				<div class="garage-car__text">
					<p class="garage-car__name">{{car.name}}</p>
					<p class="garage-car__garage-name">{{car.garageName}}</p>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data: function () {
		return {
      searchValue: "",
			cars: [
				{
					name: "Mitsubishi Lancer X",
					garageName: "Garage #1",
				},
				{
					name: "Mitsubishi Lancer X",
					garageName: "Garage #1",
				},
				{
					name: "Mitsubishi Lancer X",
					garageName: "Garage #1",
				},
				{
					name: "Mitsubishi Lancer X",
					garageName: "Garage #1",
				},
				{
					name: "Mitsubishi Lancer X",
					garageName: "Garage #1",
				},
				{
					name: "Mitsubishi Lancer X",
					garageName: "Garage #1",
				},
				{
					name: "Mitsubishi Lancer X",
					garageName: "Garage #1",
				},
				{
					name: "Mitsubishi Lancer X",
					garageName: "Garage #1",
				},
			],
		};
	},
};
</script>

<style lang="scss">
.garage-car {
	display: flex;
	align-items: center;
	gap: 0.4vw;

	padding: 0.6vw 0.75vw;

	background: rgba(17, 16, 30, 0.5);

	border: 0.1vw solid #ffffff20;
	border-radius: 0.5vw;

  transition: filter 100ms ease-out;
  &:hover {
    filter: drop-shadow(0 0 .5vw rgba(73, 69, 124, 0.5))
  }

	&__icon {
		width: 2.5vw;
	}
	&__text {
		display: flex;
		flex-direction: column;
		gap: 0.1vw;
	}
	&__name {
    font-size: .9vw;
    font-weight: 700;

		background: linear-gradient(221.49deg, #007aff -56.61%, #fa00ff 121.23%),
			#ffffff;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}

  &__garage-name {
    font-size: .8vw;
    font-weight: 700;

    color: white;
    opacity: .25;
  }
}

.garage-search {
	display: flex;
	gap: 0.4vw;

	padding: 0.5vw 0.75vw;

	background-color: #0b0a16;

	border-radius: 0.5vw;

  &__icon {
    width: .9vw;
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
}

.garage-screen {
	display: flex;
	flex-direction: column;
	gap: 0.25vw;

	background: url("../../assets/img/garage-screen/background.svg");
	background-size: 100% 100%;

	padding: 1vw;
	padding-top: 2vw;

	&__title {
		font-size: 1.5vw;
		font-weight: 700;

		line-height: 1;
	}

	&__cars {
    display: flex;
    flex-direction: column;

    flex-grow: 1;

    padding-right: .25vw;

    overflow: auto;

    gap: .4vw;

    &::-webkit-scrollbar {
      width: .2vw;
    }
    &::-webkit-scrollbar-track {
      background: #522644;
    }
    &::-webkit-scrollbar-thumb {
      background: #e33ee6;
    }
	}

	&__car {
	}
}
</style>