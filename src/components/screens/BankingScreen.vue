<template>
	<div class="banking-screen screen">
		<p class="banking-screen__title screen-title-text">Banking</p>
		<div class="banking-screen__greeting banking-greeting">
			<img class="banking-greeting__avatar" :src="holderAvatar" />
			<p class="banking-greeting__text purple-gradient-text">
				<span class="banking-greeting__small-text">Hello,</span>
				<br />
				{{holderName}}!
			</p>
		</div>
		<div class="banking-screen__card banking-card">
			<div class="banking-card__header">
				<img class="banking-card__dollar-icon" src="@/assets/img/banking-screen/dollar-icon.svg" />
				<div>
					<p class="banking-card__bank-name purple-gradient-text">{{bankName}}</p>
					<p class="banking-card__money-value">$ {{money}}</p>
				</div>
			</div>
			<div class="banking-card__additional-info">
				<div class="banking-card__iban">
					<p class="banking-card__info-label">IBAN:</p>
					<p class="banking-card__info-value">{{iban}}</p>
				</div>
				<div class="banking-card__gultig-bis">
					<p class="banking-card__info-label">Gultig bis:</p>
					<p class="banking-card__info-value">{{gultigBis}}</p>
				</div>
			</div>
		</div>
		<div class="banking-screen__section banking-section" v-if="isSendSectionActive">
			<p class="banking-section__label">Money Transaction</p>
			<div class="banking-screen__send-money banking-send-money">
				<input
					class="banking-send-money__input"
					placeholder="Type user name"
					v-model="sendMoney.counteragentName"
				/>
				<input class="banking-send-money__input" placeholder="Amount" v-model="sendMoney.value" />
			</div>
		</div>
		<Button theme="banking" :onClick="onSendMoneyClick">Send Money</Button>
		<div class="banking-screen__section banking-section" v-if="isTransactionsSectionActive">
			<p class="banking-section__label">History of transactions</p>
			<div class="banking-screen__transactions">
				<div
					class="banking-screen__transaction banking-transaction"
					v-for="transaction in recentTransactions"
				>
					<img
						class="banking-transaction__icon"
						:src="transaction.type === 'incoming' ? require('@/assets/img/banking-screen/incoming-transaction-icon.svg') : require('@/assets/img/banking-screen/outcoming-transaction-icon.svg')"
					/>
					<div class="banking-transaction__text">
						<p
							class="banking-transaction__counteragent-name purple-gradient-text"
						>{{transaction.counteragentName}}</p>
						<p
							:class="`banking-transaction__value banking-transaction__value_type_${transaction.type}`"
						>${{transaction.value}}</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import avatar from "../../assets/img/banking-screen/avatar.png";

import Button from "../Button.vue";

export default {
	components: { Button },
	data: function () {
		return {
			isTransactionsSectionActive: true,
			isSendSectionActive: false,

			holderAvatar: avatar,
			holderName: "Romario Richardson",
			bankName: "Mikhayloff Arts BANK",
			money: 650000000,
			iban: "2QT7 6565 7777 8888 8888",
			gultigBis: "2025",
			recentTransactions: [
				{
					counteragentName: "John Dorian JR.",
					value: 650000000,
					type: "incoming",
				},
				{
					counteragentName: "John Dorian JR.",
					value: 650000000,
					type: "outcoming",
				},
				{
					counteragentName: "John Dorian JR.",
					value: 650000000,
					type: "incoming",
				},
				{
					counteragentName: "John Dorian JR.",
					value: 650000000,
					type: "outcoming",
				},
			],
			sendMoney: {
				counteragentName: "",
				value: "",
			},
		};
	},
  methods: {
    onSendMoneyClick: function() {
      console.log("KEK");
      if(!this.isSendSectionActive) {
        this.isSendSectionActive = true;
        this.isTransactionsSectionActive = false;
      } else {
        // TODO: Add send money handler
      }
    }
  }
};
</script>

<style lang="scss">
.banking-send-money {
	display: flex;
	flex-direction: column;
	gap: 0.25vw;

	&__input {
		width: 100%;

		box-sizing: border-box;
		padding: 1vw 0.75vw;

		font-size: 0.9vw;
		font-weight: 700;
		text-align: center;

		color: white;
		background: rgba(17, 16, 30, 0.5);

		border: 0.1vw solid #ffffff20;
		border-radius: 0.5vw;
		outline: none;

		&::placeholder {
			opacity: 0.55;
		}
	}
}

.banking-transaction {
	display: flex;
	align-items: center;
	gap: 0.75vw;

	padding: 0.6vw 0.75vw;

	background: rgba(17, 16, 30, 0.5);

	border: 0.1vw solid #ffffff20;
	border-radius: 0.5vw;

	&__icon {
		width: 2.5vw;
	}
	&__text {
		display: flex;
		flex-direction: column;
		gap: 0.1vw;
	}
	&__counteragent-name {
		font-size: 0.9vw;
		font-weight: 700;
	}

	&__value {
		font-size: 0.8vw;
		font-weight: 700;

		color: white;

		&_type {
			&_incoming {
				&::before {
					content: "+";
				}

				color: #00ea9a;
			}
			&_outcoming {
				&::before {
					content: "-";
				}

				color: #ff4646;
			}
		}
	}
}

.banking-section {
	display: flex;
	flex-direction: column;
	gap: 0.25vw;

	&__label {
		font-size: 0.6vw;
		font-weight: 600;

		opacity: 0.55;
	}
}

.banking-card {
	display: flex;
	flex-direction: column;
	justify-content: space-between;

	height: 7vw;

	padding: 0.5vw;

	background: url("../../assets/img/banking-screen/card-background.svg");
	background-size: 100% 100%;

	border-radius: 0.5vw;

	&__header {
		display: flex;
		align-items: center;
		gap: 0.5vw;
	}

	&__dollar-icon {
		width: 2.5vw;
	}

	&__bank-name {
		font-size: 0.9vw;
		font-weight: 700;
	}

	&__money-value {
		margin-top: 0.2vw;

		font-size: 0.9vw;
		font-weight: 700;

		color: #3bd738;
	}

	&__additional-info {
		display: flex;
		justify-content: space-between;
	}
	&__gultig-bis {
		text-align: right;
	}

	&__info-label {
		font-size: 0.6vw;
		font-weight: 600;

		color: white;
		opacity: 0.3;
	}
	&__info-value {
		margin-top: 0.15vw;

		font-size: 0.75vw;
		font-weight: 600;
	}
}

.banking-greeting {
	display: flex;
	gap: 0.25vw;

	&__avatar {
		width: 2vw;
	}

	&__text {
		font-size: 0.9vw;
		font-weight: 700;
	}

	&__small-text {
		font-size: 0.65vw;
	}
}

.banking-screen {
	display: flex;
	flex-direction: column;
	gap: 0.4vw;

	background: url("../../assets/img/garage-screen/background.svg");
	background-size: 100% 100%;

	padding: 0.5vw;
	padding-top: 2vw;

	&__card {
		flex-shrink: 0;
	}

	&__section {
		overflow: hidden;
	}

	&__transactions {
		display: flex;
		flex-direction: column;
		flex-grow: 1;
		gap: 0.25vw;

		overflow: auto;

		&::-webkit-scrollbar {
			width: 0.2vw;
		}
		&::-webkit-scrollbar-track {
			background: #522644;
		}
		&::-webkit-scrollbar-thumb {
			background: #e33ee6;
		}
	}
}
</style>