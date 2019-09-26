<template>
  <div>
    <div v-if="kk==1">
      <GoodLits :goodId="1"></GoodLits>
    </div>
    <div v-else-if="kk==2">
      <GoodLits :goodId="2"></GoodLits>
    </div>
    <div v-else-if="kk==3">
      <GoodLits :goodId="3"></GoodLits>
    </div>
    <div v-else>
      <GoodLits :goodId="0"></GoodLits>
    </div>
  </div>
</template>

<script>
import VueEvent from "./VueEvent";
import GoodLits from "./GoodList";
export default {
  data() {
    return {
      kk: 0
    };
  },
  mounted() {
    VueEvent.$on("val", m => {
      this.kk = m;
    });
  },
  components: {
    GoodLits
  }
};
</script>

<style>
</style>