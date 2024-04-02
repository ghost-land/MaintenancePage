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
            <br><b
              >Ghost eShop is facing difficulties due to server costs. Please read this message.​</b><br />
            Ghost eShop needs you to pay for the servers, because the sites and
            especially the cdn and applications cost a certain amount every
            month. The donations will be used mainly to pay the servers and
            the projects such as the WiiU DB, BETA 3DS.
            Here are the different costs:<br />
            - Cost of the main server: 200$/month<br />
            - Estimated cost of the proxy : 100$/month<br />
            - DDOS Protection + VM for Proxy cost : 200$/month<br />
            - Maintenance cost (backup, domain name...) : 50$/month<br />
            - Other cost : 20$/month<br />This
            makes a total cost of more than 570$ per month (6840$/year). If we manage to
            raise this 6840$, we will have enough money to continue the Ghost
            eShop project for another year.<br />
            <br>Ghost eShop will remain free for life, but unfortunately for members of
            the Ghost Land Team and Ghost eShop Team, it has become difficult to afford
            the monthly cost of over $570. It's important to note that the Ghost eShop Team
            consists of a small team of 3 developers and 3 other members (such as graphic designers).
            Therefore, we are requesting donations to keep Ghost eShop operational.
            Once we receive the sum of $570, we will be able to cover the server costs,
            and everything will function perfectly again.<br
            >We sincerely apologize for any inconvenience and ask for your understanding.<br />
            <br /><b
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
