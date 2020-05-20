<template>
  <v-app>
    <!-- Drawer -->
    <v-navigation-drawer app v-model="drawer" clipped>
      <v-container>
        <v-list-item>
          <v-list-item-title class="title grey--text text--darken-2">
            Navigation Listts
          </v-list-item-title>
        </v-list-item>
        <v-divider></v-divider>
        <v-list dense nav>
          <v-list-item v-for="nav_list in nav_lists" :key="nav_list.name" >
            <v-list-item-icon>
              <v-icon>{{ nav_list.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title>{{ nav_list.name }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-container>
    </v-navigation-drawer>

    <!-- Navbar -->
    <v-app-bar app clipped-left>
      <v-app-bar-nav-icon @click="drawer=!drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Vuetify</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items>
      <v-btn text>For Enterprise</v-btn>
      <v-menu offset-y>
        <template v-slot:activator="{on}">
          <v-btn v-on="on" text>Support<v-icon>mdi-menu-down</v-icon></v-btn>
        </template>
        <v-list>
          <v-list-item v-for="(item, index) in items" :key="index">
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title>{{ item.name }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-menu>
      </v-toolbar-items>
    </v-app-bar>
    <v-content>
        <router-view />
      </v-content>
  </v-app>
</template>
<script>

/*
<v-toolbar-items /height 100
  <v-btn
    text        /なんもなし
    outlined    /外枠

<template v-slot:activator="{on}">
  <v-btn v-on="on" text>Support</v-btn>
</template>
<v-list>
  <v-list-item>
    <v-list-item-content>
      <v-list-item-title>contents</v-list-item-title>
    </v-list-item-content>
  </v-list-item>
</v-list>
*/
export default {
  data() {
    return {
      drawer: null,
      nav_lists: [
        {name: 'Getting Stawrted', icon: 'mdi-vuetify', lists: ['Quick Start', 'Pre-made layouts']},
        {name: 'Customization', icon: 'mdi-cogs'},
        {name: 'Styles & animations', icon: 'mdi-palette'},
      ],
      items: [
        {name: 'Consulting and Support', icon: 'mdi-vuetify'},
        {name: 'Discord community', icon: 'mdi-discord'},
        {name: 'Report a bug', icon: 'mdi-bug'}
      ]
    }
  },
};
</script>
