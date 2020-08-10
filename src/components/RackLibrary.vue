<template>
  <v-list dense>
    <v-list-item v-for="(rack, idx) of library.getters.racks" :key="idx">
      <v-list-item-action>
        <v-icon @click="store.commit('addRack', rack)">mdi-view-dashboard</v-icon>
      </v-list-item-action>
      <v-list-item-content>
        <v-list-item-title>{{rack.model}}</v-list-item-title>
      </v-list-item-content>
    </v-list-item>
  </v-list>
</template>

<script>
export default {
  props: { library: Object, store: Object },

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
}
</style>
