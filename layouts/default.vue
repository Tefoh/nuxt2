<template>
  <v-app dark>
    <v-navigation-drawer v-model="drawer" fixed app right>
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
    <v-app-bar fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="'alaatv - پنل کاربری'" />
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer absolute app>
      <span>
        تمامی حقوق برای alaatv محفوظ است. &copy;
        {{ new Date().getFullYear() }}
      </span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'default',
  data() {
    return {
      drawer: true,
      items: [
        {
          icon: 'mdi-account',
          title: 'پروفایل',
          to: '/',
        },
      ],
    }
  },
}
</script>
