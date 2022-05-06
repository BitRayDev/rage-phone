<template>
  <div class="fractions-list-screen">
    <div class="fraction-app__general-info fractions-general-info">
      <div class="fractions-general-info__header">
        <p class="fractions-general-info__title">Fractions are available</p>
        <p class="fractions-general-info__subtitle">{{ fractions.length }} fractions are here</p>
      </div>
      <div class="fractions-general-info__members-info fractions-members-info">
        <div class="fractions-members-info__header">
          <p class="fractions-members-info__title">Members online at all</p>
          <p class="fractions-members-info__members-amount">{{ membersOnlineAtAll }}</p>
        </div>
        <div class="fractions-members-info__bar">
          <div class="fractions-members-info__bar-fill" :style="{ width: `${membersBarFillValue}%` }"/>
        </div>
      </div>
    </div>
    <div class="fraction-app__fractions">
      <FractionCard class="fraction-app__fraction-card" @click.native="$emit('fraction-click', fraction)" v-for="fraction in fractions"
                    :fraction="fraction"
                    :buttons="[{theme: 'fraction-primary', title: 'Check'}]"/>
    </div>
  </div>
</template>

<script>
import FractionCard from "./FractionCard";

export default {
  name: "FractionsListScreen",
  components: {FractionCard},
  props: {
    fractions: Array
  },
  computed: {
    membersOnlineAtAll: function () {
      return this.fractions.reduce((accumulator, fraction) => accumulator + fraction.members.filter(member => member.isOnline).length, 0);
    },
    maxMembersAtAll: function () {
      return this.fractions.reduce((accumulator, fraction) => accumulator + fraction.members.length, 0);
    },
    membersBarFillValue: function () {
      return this.membersOnlineAtAll / this.maxMembersAtAll * 100;
    }
  }
}
</script>

<style scoped>

</style>