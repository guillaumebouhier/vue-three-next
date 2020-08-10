<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app clipped>
      <RackLibrary :library="library" :store="store"></RackLibrary>
    </v-navigation-drawer>

    <v-app-bar app clipped-left>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Virtual Guitar Rack</v-toolbar-title>
    </v-app-bar>

    <RackDisplay :store="store"></RackDisplay>

    <v-footer app>
      <span>&copy; 2020</span>
    </v-footer>
  </v-app>
</template>

<script>
import RackDisplay from "./RackDisplay";
import RackLibrary from "./RackLibrary";
export default {
  components: {
    RackDisplay,
    RackLibrary,
  },
  props: { store: Object, library: Object },

  data: () => ({
    drawer: null,
  }),
  created() {
    // this.$vuetify.theme.dark = true;
  },
  methods: {
    rackImage(imgUrl) {
      return require("@/assets/" + imgUrl);
    },
  },
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
