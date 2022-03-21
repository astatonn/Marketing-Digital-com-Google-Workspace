<template>
  <div id="app">
    <v-app id="inspire">
      <!-- <v-navigation-drawer
        v-model="drawer"
        app
    >
      <v-sheet
        color="grey lighten-4"
        class="pa-4"
      >
        <v-avatar>
          <img
            src="https://tc.com.br/wp-content/uploads/2021/07/steve-jobs.jpg"
            alt="John"
          >
        </v-avatar>
        <div>josemaria@gmail.com</div>
      </v-sheet>
      <v-divider></v-divider>
      <v-list>
        <v-list-item
          v-for="[icon, text] in links"
          :key="icon"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
    </v-app-bar> -->
    
            
      <v-card 
        color="grey lighten-4"
        flat
        height="1000px" class="photo1"
        tile
      >
        <v-img
        >

        </v-img>
        <v-toolbar dense class="photo1">
          <v-app-bar-nav-icon
          color="white">
          </v-app-bar-nav-icon>

          <v-spacer></v-spacer>
 
    
          <v-btn icon>
            <v-icon
            color="white">
            mdi-twitter
            </v-icon>
          </v-btn>

          <v-btn icon>
            <v-icon
            color="white">
            mdi-facebook
            </v-icon>
          </v-btn>
    
          <v-btn icon>
            <v-icon
            color="white">
            mdi-linkedin</v-icon>
          </v-btn>
    
          <v-btn icon>
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>

          <v-img class = "logo"
            lazy-src="https://picsum.photos/id/11/10/6"
            max-height="150"
            max-width="250"
            src="src/img/logo.png"
          ></v-img>

        </v-toolbar>
      </v-card>
    </v-app>
  </div>


</template>

    <v-main>
      <!--  -->
    </v-main>

<script>
  export default {
    data: () => ({ drawer: null,
      links: [
        ['mdi-account', 'Conta'],
        ['mdi-cart', 'Assinatura'],
        ['mdi-logout', 'Logout'],
        ],
    }),
  }
</script>

<style scoped>



</style>