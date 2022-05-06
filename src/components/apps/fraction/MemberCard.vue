<template>
  <div class="member-card">
    <div class="member-card__online-indicator" :style="{backgroundColor: member.isOnline ?'#3BD738' : '#FF4646'}"/>
    <div class="member-card__properties">
      <div class="member-card__property">
        <p class="member-card__property-label">User name</p>
        <p class="member-card__property-value">{{member.name}}</p>
      </div>
      <div class="member-card__property">
        <p class="member-card__property-label">Rank</p>
        <p class="member-card__property-value">{{member.rank}}</p>
      </div>
      <div class="member-card__property">
        <p class="member-card__property-label">Phone number</p>
        <p class="member-card__property-value">{{member.phoneNumber}}</p>
      </div>
    </div>
    <div class="member-card__buttons">
      <Button theme="fraction-danger" @click.native="$emit('uninvite-click')">Uninvite</Button>
      <Button theme="fraction-danger" @click.native="$emit('take-rank-click')">Take Rank</Button>
      <Button theme="fraction-success" @click.native="$emit('give-rank-click')">Give Rank</Button>
    </div>
  </div>
</template>

<script>
import Button from "../../Button";
export default {
  name: "MemberCard",
  components: {Button},
  props: {
    member: Object
  }
}
</script>

<style lang="scss" scoped>
.member-card {
  display: flex;
  flex-direction: column;
  gap: .25vw;

  padding: .25vw .5vw;

  background: #171920;
  border-radius: .25vw;

  position: relative;

  &__online-indicator {
    position: absolute;
    right: -.25vw;
    top: .5vw;

    height: .6vw;
    width: .6vw;

    border-radius: 100vw;
  }

  &__properties {
    display: flex;
    justify-content: space-between;
    gap: .25vw;
  }
  &__property {
    display: flex;
    flex-direction: column;
    width: 30%;
    gap: .25vw;
  }
  &__property-label {
    color: rgba(255, 255, 255, 0.2);

    font-size: .7vw;
    font-weight: 500;
  }
  &__property-value {
    font-size: .7vw;
    font-weight: 600;
  }
  &__buttons {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: .25vw;
  }
}
</style>