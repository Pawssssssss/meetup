<template>
  <v-app>
    <v-app-bar>
      <v-toolbar>
        <v-app-bar-nav-icon @click="sideNav = !sideNav"></v-app-bar-nav-icon>
        <v-toolbar-title>
          <router-link to="/" class="custom-link">MusicMeetups</router-link>
        </v-toolbar-title>
        <v-toolbar-items>
          <v-btn prepend-icon="mdi-music-circle" variant="flat">
            View Meetups
          </v-btn>
        </v-toolbar-items>
      </v-toolbar>
    </v-app-bar>

    <v-layout>
      <v-navigation-drawer v-model="sideNav">
        <v-list>
          <v-list-item prepend-icon="mdi-music-circle" title="MusicEvents"></v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list density="compact" nav>
          <v-list-item v-for="item in menuItems" :key="item.title">
            <v-list-item-action>
              <router-link :to="item.link" class="custom-link">
                <div class="d-flex align-center">
                  <v-icon class="icon">{{ item.icon }}</v-icon>
                  <v-list-item-title class="title">{{ item.title }}</v-list-item-title>
                </div>
              </router-link>
            </v-list-item-action>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </v-layout>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      sideNav: false,
      menuItems: [
        { icon: 'mdi-account-supervisor', title: 'View Meetups', link: '/event' },
        { icon: 'mdi-map-marker', title: 'Organize Meetups', link: '/event/new' },
        { icon: 'mdi-account', title: 'Profile', link: '/profile' },
        { icon: 'mdi-face-man', title: 'Sign up', link: '/signup' },
        { icon: 'mdi-lock-open', title: 'Sign in', link: '/signin' },
      ]
    }
  }
}
</script>

<style>
.custom-link {
  text-decoration: none;
  /* Remove the underline */
  color: inherit;
  /* Use the same color as the parent element */
}

.custom-link:hover {
  color: red;
}

.icon {
  margin-right: 10px;
}

.title {
  margin-left: 10px;
}
</style>