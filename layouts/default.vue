<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      color="#f0f0f0"
      fixed
      app
    >
      <v-list-item>
        <v-list-item-icon class="ma-auto">
          <img id="hokcafe__logo" src="/img/hokcafe__logo.svg" alt="北大カフェプロジェクト">
        </v-list-item-icon>
      </v-list-item>

      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <!-- <v-btn
        icon
        @click.stop="clipped = !clipped"
      >
        <v-icon>mdi-application</v-icon>
      </v-btn> -->
      <!-- <v-btn
        icon
        @click.stop="fixed = !fixed"
      >
        <v-icon>mdi-minus</v-icon>
      </v-btn> -->
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <!-- <v-btn
        icon
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn> -->
    </v-app-bar>
    <v-main>
      <v-container
        fluid
        class="fill-height pa-0"
      >
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer
      fixed
      app
    >
      <span>&copy; {{ new Date().getFullYear() }} Hokudai Café Project</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: true,
      drawer: false,
      items: [
        {
          icon: 'mdi-home',
          title: 'Home',
          to: '/'
        },
        {
          icon: 'mdi-office-building',
          title: 'About',
          to: '/about'
        },
        {
          icon: 'mdi-account-group',
          title: 'Member',
          to: '/member'
        },
        {
          icon: 'mdi-coffee',
          title: 'Café',
          to: '/cafe'
        },
        {
          icon: 'mdi-newspaper',
          title: 'News',
          to: '/news'
        },
        {
          icon: 'mdi-link-variant',
          title: 'Link',
          to: '/link'
        },
        {
          icon: 'mdi-send',
          title: 'Contact',
          to: '/contact'
        }
      ],
      miniVariant: false,
      title: 'Hokudai Café Project',
      headerHeight: 0
    }
  },
}
</script>

<style lang="scss" scoped>
header {
  height: 64px !important;
}

#hokcafe__logo {
  max-width: 100%;
}

.on-hover {
  background-color: red;
}
</style>
