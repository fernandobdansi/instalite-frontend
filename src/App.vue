<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app clipped>
      <v-list dense>
        <v-list-item :key="i" v-for="(route, i) in $router.options.routes" link :to="route.path">
          <v-list-item-content>
            <v-list-item-title>{{ route.name }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app clipped-left>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>InstaLite</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <v-container fluid>
        <v-row>
          <v-col>
            <router-view />
          </v-col>
        </v-row>
      </v-container>
    </v-main>

    <v-footer app class="justify-center">
      <span>&copy; 2020 | InstaLite</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  props: {
    source: String
  },

  data: () => ({
    drawer: null
  }),

  created() {
    this.$vuetify.theme.dark = false;
  }
};
</script>