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
        <v-list-tile
          value="true"
          v-for="(item, i) in items"
          :key="i"
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      app
      :clipped-left="clipped"
    >
      
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>
      </v-btn>

      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
    <v-navigation-drawer
      temporary
      :right="right"
      v-model="rightDrawer"
      fixed
      app
    >
    </v-navigation-drawer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      items: [{
        icon: 'bubble_chart',
        title: 'Années 1950', 
      },
      {
        icon: 'bubble_chart',
        title: 'Années 1960',
      },
      {
        icon: 'bubble_chart',
        title: 'Années 1970',
      },
      {
        icon: 'bubble_chart',
        title: 'Années 1980',
      },
      {
        icon: 'bubble_chart',
        title: 'Années 1990',
      },
      {
        icon: 'bubble_chart',
        title: 'Années 2000',
      },
      {
        icon: 'bubble_chart',
        title: 'Années 2010',
      }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'The web from 1950 to 2018'
    }
  },
  name: 'App'
}
</script>
