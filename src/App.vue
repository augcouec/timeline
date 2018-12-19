<template>
  <v-app>
    <v-navigation-drawer
      persistent
      :mini-variant="miniVariant"
      :clipped="clipped"
      v-model="drawer"
      enable-resize-watcher
      fixed
      app
    >
      <v-list>
        <v-list-tile value="true" v-for="(item, i) in items" :key="i">
          <v-list-tile-action>
            <v-icon v-html="item.icon" class="grey--text"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" class="grey--text"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar app :clipped-left="clipped">
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-spacer></v-spacer>
      <v-toolbar-title centered v-text="title" class="black--text headline"></v-toolbar-title>
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      items: [
        {
          icon: "hourglass_empty",
          title: "Années 1950"
        },
        {
          icon: "hourglass_empty",
          title: "Années 1960"
        },
        {
          icon: "hourglass_empty",
          title: "Années 1970"
        },
        {
          icon: "hourglass_empty",
          title: "Années 1980"
        },
        {
          icon: "hourglass_empty",
          title: "Années 1990"
        },
        {
          icon: "hourglass_empty",
          title: "Années 2000"
        },
        {
          icon: "hourglass_empty",
          title: "Années 2010"
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "The web from 1950 to 2018"
    };
  },
  name: "App"
};
</script>
