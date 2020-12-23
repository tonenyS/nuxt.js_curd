<template>
  <v-app>
    <v-main>
      <v-app-bar color="white" elevate-on-scroll>
        <v-app-bar-nav-icon
          elevation-0
          @click.stop="drawer = !drawer"
        ></v-app-bar-nav-icon>
        <v-toolbar-title>CRUD</v-toolbar-title>
      </v-app-bar>
      <v-container><nuxt /></v-container>
    </v-main>
    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list-item>
        <v-list-item-avatar>
          <v-img
            src="https://scontent.fbkk5-5.fna.fbcdn.net/v/t1.0-1/p200x200/48385328_2004646086283034_6393444460914540544_o.jpg?_nc_cat=104&ccb=2&_nc_sid=7206a8&_nc_eui2=AeEr4qDn_MUCNYopugBAIp67BJ138YzmRKYEnXfxjOZEpnCnREemHkHxh8sHTPBAl7b8HQ4KkY40MhCM3mbshxsQ&_nc_ohc=51Qwq_1n4ioAX-8i3EZ&_nc_ht=scontent.fbkk5-5.fna&tp=6&oh=0a5d09640fab840320279fa5949c39a1&oe=600AC231"
          ></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>Mahidon Thaipuvnart</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <NuxtLink
          v-for="item in items"
          :key="item.title"
          :to="item.route"
          class="text-decoration-none"
        >
          <v-list-item link>
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </NuxtLink>
      </v-list>
    </v-navigation-drawer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: null,
      items: [
        { title: 'Home', icon: 'mdi-view-dashboard', route: '/' },
        { title: 'List', icon: 'mdi-animation', route: '/company/list' },
        { title: 'Add', icon: 'mdi-account-plus', route: '/company/add' },
      ],
    }
  },
}
</script>
