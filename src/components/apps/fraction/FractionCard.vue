<template>
  <div class="fraction-card">
    <div class="fraction-card__section fraction-card__section_type_general">
      <p class="fraction-card__name-label">Fraction name</p>
      <p class="fraction-card__name">{{ fraction.name }}</p>
      <div class="fraction-card__buttons">
        <Button class="fraction-card__button" v-for="button in buttons" :theme="button.theme" @click.native="button.onClick">
          {{ button.title }}
        </Button>
      </div>
    </div>
    <div class="fraction-card__section fraction-card__section_type_online">
      <CircleProgressBar :icon="require('@/assets/img/icons/user.svg')" :value="membersOnline"
                         :max-value="maxMembers" color="#95E6CB"/>
      <p class="fraction-card__online-label">online</p>
    </div>
  </div>
</template>

<script>
import Button from "../../Button";
import CircleProgressBar from "../../CircleProgressBar";

export default {
  name: "FractionCard",
  components: {CircleProgressBar, Button},
  props: {
    fraction: Object,
    buttons: Array,
  },
  computed: {
    membersOnline: function () {
      return this.fraction.members.filter(member => member.isOnline).length;
    },
    maxMembers: function () {
      return this.fraction.members.length;
    },
  }
}
</script>

<style lang="scss" scoped>
.fraction-card {
  display: flex;
  justify-content: space-between;
  gap: .5vw;

  padding: .5vw .75vw;

  background: #171920;
  border-radius: .3vw;

  transition: box-shadow 100ms ease-out;
  &:hover {
    box-shadow: 0 0 1vw rgba(255, 255, 255, 0.05);
  }

  &__name-label {
    color: rgba(255, 255, 255, 0.2);

    font-size: .8vw;
    font-weight: 500;
  }

  &__name {
    color: white;

    font-size: 1vw;
    font-weight: 600;

    line-height: 1.1;
  }

  &__online-label {
    color: rgba(255, 255, 255, 0.2);

    font-size: .75vw;
    font-weight: 500;
  }

  &__section {
    display: flex;
    flex-direction: column;
    &_type {
      &_general {
        gap: .25vw;
      }
      &_online {
        justify-content: center;
        align-items: center;
      }
    }
  }
  &__buttons {
    display: flex;
    flex-wrap: wrap;
    gap: .25vw;
  }
  &__button {
    width: fit-content;
    flex-shrink: 0;
  }
}
</style>