<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
      color="#F4D03F"
    >
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
    <v-app-bar :clipped-left="clipped" fixed app color="#7B7D7D">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn class="ma-1 col-" color="#F4D03F" to="/">
        Search
        <v-icon right dark>mdi mdi-magnify mdi-18px</v-icon></v-btn
      >
      <v-btn class="ma-1 col-" color="#F4D03F" to="/track">Track</v-btn>
      <v-btn class="ma-1 col-" color="#F4D03F" to="/login">Login</v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>

    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-qrcode-scan',
          title: 'Tracking Number',
          to: '/track',
        },
        {
          icon: 'mdi-account',
          title: 'Service',
          to: '/customer',
        },
        {
          icon: 'mdi-account-edit',
          title: 'Customer List Data',
          to: '/listdata',
        },
        {
          icon: 'mdi-barcode-scan',
          title: 'Update Status',
          to: '/update',
        },
        {
          icon: 'mdi-folder',
          title: 'Summary report',
          to: '/data',
        },
        {
          icon: 'mdi-comment',
          title: 'Contact Us',
          to: '/contact',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Fast Tracking Service',
    }
  },
}
</script>
