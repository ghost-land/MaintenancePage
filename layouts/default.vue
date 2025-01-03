<template>
  <v-app dark>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-toolbar-title v-text="title" />
      <v-spacer></v-spacer>
      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            icon
            v-bind="attrs"
            v-on="on"
          >
            <v-icon>mdi-translate</v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item
            v-for="locale in $i18n.locales"
            :key="locale.code"
            @click="$i18n.setLocale(locale.code)"
          >
            <v-list-item-title>{{ locale.name }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      <v-btn icon @click="toggleTheme">
        <v-icon>{{ $vuetify.theme.dark ? 'mdi-weather-sunny' : 'mdi-weather-night' }}</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer padless>
    <v-card
      flat
      tile
      :color="$vuetify.theme.dark ? 'black' : 'grey lighten-3'"
      class="text-center footer"
    >
      <v-card-text>
        <v-btn
          class="mx-4"
          :href="links.social.status"
          icon
        >
          <v-icon size="24px">mdi-chart-line</v-icon>
        </v-btn>
        <v-btn class="mx-4"
          :href="links.social.community"
          icon>
          <v-icon size="24px">mdi-account-group</v-icon>
        </v-btn>
        <v-btn class="mx-4"
          :href="links.social.wiki"
          icon>
          <v-icon size="24px">mdi-book-open-page-variant</v-icon>
        </v-btn>
      </v-card-text>
      <v-divider></v-divider>
      <v-card-text class="py-2">
        <small>&copy; {{ copyright }} Ghost Land Team</small>
      </v-card-text>
    </v-card>
  </v-footer>
  </v-app>
</template>

<script>
import links from '~/config/links'

export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: false,
      title: 'Ghost Land Maintenance',
      links
    }
  },
  computed: {
    copyright() {
      const startYear = 2020
      const currentYear = new Date().getFullYear()
      return currentYear > startYear ? `${startYear}-${currentYear}` : startYear
    }
  },
  methods: {
    toggleTheme() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
      // When manually toggled, stop following system preference
      localStorage.setItem('themePreference', this.$vuetify.theme.dark ? 'dark' : 'light')
    }
  },
  mounted() {
    // Check for stored preference first
    const storedPreference = localStorage.getItem('themePreference')
    if (storedPreference) {
      this.$vuetify.theme.dark = storedPreference === 'dark'
    } else {
      // Otherwise use system preference
      const prefersDark = window.matchMedia('(prefers-color-scheme: dark)')
      this.$vuetify.theme.dark = prefersDark.matches

      // Listen for system theme changes
      prefersDark.addEventListener('change', (e) => {
        if (!localStorage.getItem('themePreference')) {
          this.$vuetify.theme.dark = e.matches
        }
      })
    }
  },
}
</script>

<style>
.footer {
  width: 100% !important;
}
</style>
