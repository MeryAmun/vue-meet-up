<template>
  <v-container>
    <v-toolbar dark>
      <v-app-bar-nav-icon
        @click="sideNav = !sideNav"
        class="hidden-sm-and-up"
      ></v-app-bar-nav-icon>

      <v-toolbar-title>DevMeetUp</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only">
        <v-btn v-for="item in menuItems" :key="item.title">
          <router-link :to="item.link">
            <v-icon left dark>{{ item.icon }}</v-icon>
            {{ item.title }}
          </router-link>
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-navigation-drawer v-model="sideNav">
      <v-list>
        <v-list-item v-for="item in menuItems" :key="item.title">
          <router-link :to="item.link" class="text-decoration-none">
            <v-list-item-action>
              <v-icon> {{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>{{ item.title }}</v-list-item-content>
          </router-link>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-container>
</template>
<script>
export default {
  name: 'Header',
  data() {
    return {
      sideNav: false,
      watch: {
        group() {
          this.drawer = false
        },
      },
      menuItems: [
        {
          icon: 'mdi-account-multiple',
          title: 'view meetups',
          link: '/',
        },
        {
          icon: 'mdi-home-variant',
          title: 'Organize Meetup',
          link: '/meetup',
        },
        {
          icon: 'mdi-account-circle',
          title: 'Profile',
          link: '/profile',
        },
        {
          icon: 'mdi-account-plus',
          title: 'Sign up',
          link: '/signup',
        },
        {
          icon: 'mdi-login',
          title: 'Sign in',
          link: '/login',
        },
      ],
    }
  },
}
</script>
<style>
router-link {
  color: #0b5a33;
}
</style>
