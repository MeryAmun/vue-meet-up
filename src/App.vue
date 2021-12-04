<template>
  <v-app>
    <v-toolbar dark class="error">
      <v-app-bar-nav-icon
        @click="sideNav = !sideNav"
        class="hidden-sm-and-up"
      ></v-app-bar-nav-icon>
      <v-toolbar-title>DevMeetUp</v-toolbar-title>

      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-only">
        <v-icon dark left>mdi-account-multiple</v-icon>
        <v-btn class="error">view meetups</v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-navigation-drawer v-model="sideNav">
      <v-list>
        <v-list-item>
          <v-list-item-action>
            <v-icon> mdi-account-multiple </v-icon>
          </v-list-item-action>
          <v-list-item-content>view meetups</v-list-item-content>
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
  }),
}
</script>
