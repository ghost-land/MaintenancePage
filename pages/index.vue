<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="logo py-4 d-flex justify-center">
        <v-img
          src="favicon.ico"
          class="d-flex justify-center"
          style="padding: auto"
          max-width="128px"
        />
      </v-card>
      <v-card>
        <v-card-title class="headline"> </v-card-title>
        <v-card-text>
          <p>
            Ghost eShop needs you to pay for the servers, because the sites and
            especially the cdn and applications cost a certain amount every
            month. The donations will be used mainly to pay the new servers and
            the next projects such as the WiiU db and maybe a WiiU homebrew.
            Here are the different costs:<br />
            - Cost of the main server: 42$/month<br />
            - Estimated cost of the new server : 80$/month<br />
            - Maintenance cost (backup, domain name...) : 300$/year<br />This
            makes a total cost of more than 1300$ per year. If we manage to
            raise this 1300$, we will have enough money to continue the Ghost
            eShop project for another year.<br /><b
              >Thank you very much to all those who will make a donation as well
              as all those who already support us.</b
            >
          </p>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn href="https://ko-fi.com/ghostland"> Donate with Ko-Fi </v-btn>
          <v-btn href="https://discord.gg/a7vdfT6YPq"> Join the discord </v-btn>
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
