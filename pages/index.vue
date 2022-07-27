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
            With the various attacks we have experienced, we have decided to reconfigure our systems to improve stability and resistance to these attacks. We will come back soon, sorry for the inconvenience.
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
