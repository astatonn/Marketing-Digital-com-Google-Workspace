<template>
    <div id="app">
        <v-app id="inspire">
            <v-card class="overflow-hidden" height="2800">
                <v-app-bar color="transparent">
                    <v-app-bar-nav-icon
                        @click="drawer = true"
                        color="white"
                    ></v-app-bar-nav-icon>

                    <v-btn text color="white">Home</v-btn>
                    <v-btn text color="white">Produtos</v-btn>
                    <v-btn text color="white">Preços</v-btn>
                    <v-btn text color="white">Sobre</v-btn>
                    <v-btn text color="white">Contato</v-btn>

                    <!-- <v-spacer></v-spacer>
                   
                    <v-img class = "logo" 
                    src="src/img/logo.png"
                    ></v-img> -->

                    <v-spacer></v-spacer>

                    <v-btn icon>
                        <v-icon color="white"> mdi-twitter </v-icon>
                    </v-btn>

                    <v-btn icon>
                        <v-icon color="white"> mdi-facebook </v-icon>
                    </v-btn>

                    <v-btn icon>
                        <v-icon color="white"> mdi-linkedin</v-icon>
                    </v-btn>
                </v-app-bar>

                <v-navigation-drawer v-model="drawer" absolute temporary>
                    <v-list nav dense>
                        <v-list-item-group
                            v-model="group"
                            active-class="deep-purple--text text--accent-4"
                        >
                            <v-sheet color="grey lighten-4" class="pa-4">
                                <v-avatar>
                                    <img
                                        src="https://tc.com.br/wp-content/uploads/2021/07/steve-jobs.jpg"
                                        alt="John"
                                    />
                                </v-avatar>
                                <div>josemaria@gmail.com</div>
                            </v-sheet>
                            <v-list-item>
                                <v-list-item-icon>
                                    <v-icon>mdi-account</v-icon>
                                </v-list-item-icon>
                                <v-list-item-title>Conta</v-list-item-title>
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-icon>
                                    <v-icon>mdi-cart</v-icon>
                                </v-list-item-icon>
                                <v-list-item-title
                                    >Assinatura</v-list-item-title
                                >
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-icon>
                                    <v-icon>mdi-logout</v-icon>
                                </v-list-item-icon>
                                <v-list-item-title>Logout</v-list-item-title>
                            </v-list-item>
                        </v-list-item-group>
                    </v-list>
                </v-navigation-drawer>
            </v-card>
        </v-app>
    </div>
</template>

		<v-main>
			<!--  -->
		</v-main>

<script>
export default {
    data: () => ({
        drawer: null,
        links: [
            ["mdi-account", "Conta"],
            ["mdi-cart", "Assinatura"],
            ["mdi-logout", "Logout"],
        ],
    }),
};
</script>
