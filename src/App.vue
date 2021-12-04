<template>
  <v-app>
    <v-toolbar dark class="error">
      <v-app-bar-nav-icon
        @click="sideNav = !sideNav"
        class="hidden-sm-and-up"
      ></v-app-bar-nav-icon>
      <v-toolbar-title>DevMeetUp</v-toolbar-title>

      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only">
        <v-btn class="error" v-for="item in menuItems" :key="item.title">
          <v-icon left dark>{{ item.icon }}</v-icon>
          {{ item.title }}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-navigation-drawer v-model="sideNav">
      <v-list>
        <v-list-item v-for="item in menuItems" :key="item.title">
          <v-list-item-action>
            <v-icon> {{ item.title }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>{{ item.icon }}</v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <main></main>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  components: {},

  data: () => ({
    sideNav: false,
    menuItems: [
      {
        icon: 'mdi-account-multiple',
        title: 'view meetups',
      },
      {
        icon: 'mdi-home-variant',
        title: 'Organize Meetup',
      },
      {
        icon: 'mdi-account-circle',
        title: 'Profile',
      },

      {
        icon: 'mdi-account-plus',
        title: 'Sign up',
      },
      {
        icon: 'mdi-login',
        title: 'Sign in',
      },
    ],
  }),
}
</script>
