<template>
    <div id="app">
        <v-app id="inspire">
            <v-navigation-drawer v-model="drawer" absolute temporary app>
                <v-list nav dense>
                    <v-list-item-group 
                        
                        active-class="deep-purple--text text--accent-4"
                    >
                        <v-sheet>
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
                            <v-list-item-title>Assinatura</v-list-item-title>
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
            
            <v-app-bar 
            app 
			extension
            flat
            width="100%">

                <v-app-bar-nav-icon
                    @click="drawer = true"
                ></v-app-bar-nav-icon>

				<v-avatar tile size="70">
					<v-img src="src/img/logo.png"></v-img>
				</v-avatar>

                <v-spacer></v-spacer>

                <v-btn text class="cor_letras_menu">Home</v-btn>
                <v-btn text class="cor_letras_menu">Produtos</v-btn>
                <v-btn text class="cor_letras_menu">Preços</v-btn>
                <v-btn text class="cor_letras_menu">Sobre</v-btn>
                <v-btn text class="cor_letras_menu">Contato</v-btn>

            </v-app-bar>

            <v-main>
                <v-container 
					class="topo_home"
                    fluid
                    >
                    <div class="caixa_redes">
                        <v-btn icon>
                            <v-icon color="white"> mdi-twitter </v-icon>
                        </v-btn>

                        <v-btn icon>
                            <v-icon color="white"> mdi-facebook </v-icon>
                        </v-btn>

                        <v-btn icon>
                            <v-icon color="white"> mdi-linkedin</v-icon>
                        </v-btn>
                    </div>
					
					<div class="letras_rectangle9_primeira white--text">Alcance novos horizontes <br> com o seu negócio</div>

					<div class="letras_rectangle9_segunda white--text">Uma nova forma de realizar suas campanhas de Marketing <br> Digital para captação de clientes.</div>
					
					<div class=botao_saiba_mais>
						<v-btn
							rounded
							color="red"
							dark
							width="200"
							large
							>
							Saiba Mais
						</v-btn>
					</div>



                </v-container>
            </v-main>
        </v-app>
    </div>
</template>


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