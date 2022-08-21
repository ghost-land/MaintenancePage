<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="logo py-4 d-flex justify-center">
        <v-img src="favicon.ico" class="d-flex justify-center" style="padding:auto" max-width="128px" />
      </v-card>
      <v-card>
        <v-card-title class="headline">
          We're sorry, but our server is in maintenance.
        </v-card-title>
        <v-card-text>
          <p>
            We have chosen to put our server in maintenance. Learn more on our discord server.
          </p>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn
          href="https://discord.gg/a7vdfT6YPq"
        >
          Join the discord
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>
