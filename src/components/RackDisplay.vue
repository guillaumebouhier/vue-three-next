<template>
  <v-app id="inspire">
    <div v-for="(rack, idx) of store.getters.racks" :key="idx" class="rack-container">
      <img
        @click="store.commit('toggleRack', rack)"
        :src="rackImage(rack.imgUrl)"
        :class="{ disabled: !rack.activated }"
      />
    </div>
  </v-app>
</template>

<script>
export default {
  props: { store: Object },

  methods: {
    rackImage(imgUrl) {
      return require("@/assets/" + imgUrl);
    }
  }
};
</script>

<style lang="css">
.rack-container {
  display: flex;
  justify-content: center;
  padding: 10px;
  opacity: 1;
}
.disabled {
  opacity: 0.2;
}
</style>
