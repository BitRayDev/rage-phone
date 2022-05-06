<template>
  <div class="fraction-screen">
    <FractionCard class="fraction-screen__fraction-card"
                  :fraction="fraction"
                  :buttons="generalButtons"
    />
    <div class="fraction-screen__members-list" v-if="!isFormActive">
      <MemberCard class="fraction-screen__member-card" v-for="member in fraction.members" :member="member"/>
    </div>
    <div class="fraction-screen__form" v-if="isFormActive">
      <textarea
          class="fraction-screen__input"
          placeholder="Type your message for your fraction buddy’s"
          v-model="inputValue"
      />
      <Button class="fraction-screen__submit-button" theme="fraction-primary" @click.native="$emit('dispatch-submit')">
        Send message to all
      </Button>
    </div>
  </div>
</template>

<script>
import FractionCard from "./FractionCard";
import MemberCard from "./MemberCard";
import Button from "../../Button";

export default {
  name: "FractionScreen",
  components: {Button, MemberCard, FractionCard},
  props: {
    fraction: Object,
  },
  data: function () {
    return {
      isFormActive: false,
      inputValue: "",
      generalButtons: [
        {
          title: 'Back to Menu',
          theme: 'fraction-primary',
        },
        {
          title: 'Dispatch',
          theme: 'fraction-secondary',
          onClick: () => {
            this.isFormActive = !this.isFormActive;
          }
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.fraction-screen {
  display: flex;
  flex-direction: column;
  gap: .5vw;

  &__members-list {
    display: flex;
    flex-direction: column;
    gap: .25vw;
  }

  &__form {
    display: flex;
    flex-grow: 1;
    flex-direction: column;
    align-items: center;
    gap: .25vw;
    width: 100%;
  }

  &__input {
    flex-grow: 1;

    width: 100%;
    box-sizing: border-box;
    padding: .5vw;

    color: white;
    background: rgba(23, 25, 32, 0.49);
    border: .1vw solid #323745;
    border-radius: .3vw;

    font-size: .7vw;

    resize: none;
    outline: none;
  }

  &__submit-button {
    padding: .75vw;
  }
}
</style>