<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="logo py-6 d-flex justify-center">
        <v-img
          src="favicon.png"
          class="d-flex justify-center"
          max-width="128px"
        />
      </v-card>
      <v-card class="mt-6">
        <v-card-title class="text-h4 justify-center">{{ $t('maintenance') }}</v-card-title>
        <v-card-text>
          <div class="text-center">
            <p class="text-h6 mb-6">
              {{ $t('message') }}
            </p>
            <p class="text-body-1 mb-6">
              {{ $t('details') }}
            </p>

            <template v-if="showProgress">
              <v-card outlined class="mb-6 pa-4">
                <div class="text-subtitle-1 mb-2">{{ $t('maintenanceProgress') }}</div>
                <div class="d-flex justify-space-between mb-2">
                  <span class="caption">{{ formatDate(maintenanceConfig.startDate) }}</span>
                  <span class="caption">{{ formatDate(maintenanceConfig.endDate) }}</span>
                </div>
                <v-progress-linear
                  :value="progressValue"
                  color="primary"
                  height="20"
                  rounded
                >
                  <template v-slot:default="{ value }">
                    <strong>{{ Math.ceil(value) }}%</strong>
                  </template>
                </v-progress-linear>
              </v-card>
            </template>

            <v-divider class="my-6"></v-divider>

            <v-btn
              :href="links.social.donate"
              color="primary"
              class="mb-4"
              block
              large
            >
              <v-icon left>mdi-heart</v-icon>
              {{ $t('donate') }}
            </v-btn>

            <div class="d-flex flex-column align-center">
              <v-btn
                :href="links.social.status"
                color="primary"
                class="mb-4"
                block
              >
                <v-icon left>mdi-chart-line</v-icon>
                {{ $t('serviceStatus') }}
              </v-btn>
              <v-btn
                :href="links.social.community"
                color="info"
                class="mb-4"
                block
              >
                <v-icon left>mdi-account-group</v-icon>
                {{ $t('socialNetworks') }}
              </v-btn>
              <v-btn
                :href="links.social.wiki"
                color="success"
                block
              >
                <v-icon left>mdi-book-open-page-variant</v-icon>
                {{ $t('wiki') }}
              </v-btn>
            </div>
          </div>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import maintenanceConfig from '~/config/maintenance'
import links from '~/config/links'

export default {
  name: 'IndexPage',
  data() {
    return {
      maintenanceConfig,
      links,
      progressInterval: null
    }
  },
  computed: {
    showProgress() {
      return this.maintenanceConfig.startDate && this.maintenanceConfig.endDate
    },
    progressValue() {
      if (!this.showProgress) return 0

      const start = new Date(this.maintenanceConfig.startDate).getTime()
      const end = new Date(this.maintenanceConfig.endDate).getTime()
      const now = Date.now()

      if (now <= start) return 0
      if (now >= end) return 100

      return ((now - start) / (end - start)) * 100
    }
  },
  methods: {
    formatDate(dateString) {
      return new Date(dateString).toLocaleString(this.$i18n.locale, {
        month: 'short',
        day: 'numeric',
        hour: '2-digit',
        minute: '2-digit'
      })
    },
    updateProgress() {
      // Force reactivity update
      this.$forceUpdate()
    }
  },
  mounted() {
    if (this.showProgress) {
      this.progressInterval = setInterval(this.updateProgress, 1000)
    }
  },
  beforeDestroy() {
    if (this.progressInterval) {
      clearInterval(this.progressInterval)
    }
  }
}
</script>
