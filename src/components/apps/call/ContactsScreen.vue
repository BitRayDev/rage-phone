<template>
	<div class="app contacts-screen">
		<div class="contacts-screen__title">Contacts</div>
		<SearchInput theme="light" :onValueChange="onSearchValueChange" placeholder="Search by contact name"></SearchInput>
		<div class="contacts-screen__contacts-list">
			<div class="contacts-screen__contact contact" v-for="contact in contacts" v-if="isPassesFilter(contact)">
				<img class="contact__avatar" :src="contact.avatar" />
				<div class="contact__text">
					<p class="contact__name">{{contact.name}}</p>
					<p class="contact__phone-number">{{contact.phoneNumber}}</p>
					<p class="contact__last-called">{{contact.lastCalled}}</p>
				</div>
        <img class="contact__call-button" src="@/assets/img/icons/call.svg">
			</div>
		</div>
	</div>
</template>

<script>
import avatar from '../../../assets/img/avatar1.png';

import SearchInput from '../../SearchInput.vue';

export default {
	components: { SearchInput },
	data: function () {
		return {
      searchValue: "",
			contacts: [
				{
          avatar: avatar,
					name: "Romario Richardson",
					phoneNumber: "8 800 555 35 35",
          lastCalled: "Last call today"
				},
				{
          avatar: avatar,
					name: "Romario Richardson",
					phoneNumber: "8 800 555 35 35",
          lastCalled: "Last call today"
				},
				{
          avatar: avatar,
					name: "Romario Richardson",
					phoneNumber: "8 800 555 35 35",
          lastCalled: "Last call today"
				},
				{
          avatar: avatar,
					name: "Romario Richardson",
					phoneNumber: "8 800 555 35 35",
          lastCalled: "Last call today"
				},
				{
          avatar: avatar,
					name: "Romario Richardson",
					phoneNumber: "8 800 555 35 35",
          lastCalled: "Last call today"
				},
				{
          avatar: avatar,
					name: "Romario Richardson",
					phoneNumber: "8 800 555 35 35",
          lastCalled: "Last call today"
				},
			],
		};
	},

  methods: {
    onSearchValueChange: function(e) {
      this.searchValue = e.target.value;
    },

    isPassesFilter: function(contact) {
      return contact.name.toLowerCase().includes(this.searchValue.toLowerCase());
    }
  }
};
</script>

<style lang="scss">
.contact {
	display: flex;
	align-items: center;
	gap: 0.4vw;

	padding: 0.6vw 0.75vw;

	background: white;

	border: 0.1vw solid #ffffff20;
	border-radius: 0.5vw;

  transition: filter 100ms ease-out;
  &:hover {
    filter: drop-shadow(0 0 .5vw #afafaf80)
  }

	&__avatar {
		width: 2.5vw;
    
    border-radius: .5vw;
	}
	&__text {
		display: flex;
		flex-direction: column;
		gap: 0.1vw;
	}
	&__name {
    color: #200E32;

    font-size: .8vw;
    font-weight: 600;
	}
  &__phone-number {
    color: #200E32;

    font-size: .7vw;
    font-weight: 500;
	}
  &__last-called {
    color: #200E32;
    opacity: .35;

    font-size: .7vw;
    font-weight: 500;
	}
}

.contacts-screen {
	display: flex;
	flex-direction: column;
	gap: 0.25vw;

	background: #F1F1F1;
	background-size: 100% 100%;

	padding: .5vw;
	padding-top: 2vw;
  padding-bottom: 0;

	&__title {
    color: #200E32;
    
		font-size: 1.5vw;
		font-weight: 700;

		line-height: 1;
	}

	&__contacts-list {
    display: flex;
    flex-direction: column;

    flex-grow: 1;

    padding-right: .25vw;
    padding-bottom: .5vw;

    overflow: auto;

    gap: .4vw;

    &::-webkit-scrollbar {
      width: .2vw;
    }
    &::-webkit-scrollbar-track {
      background: #e6e6e6;
    }
    &::-webkit-scrollbar-thumb {
      background: #c4c4c4;
    }
	}

	&__contact {
	}
}
</style>