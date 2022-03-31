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
				width="100%"
				class="cabecalho"
			>

                <v-app-bar-nav-icon
                    @click="drawer = true"
                ></v-app-bar-nav-icon>

				<v-avatar class="logo" tile size="70">
					<v-img src="src/img/logo.png"></v-img>
				</v-avatar>

                <v-spacer></v-spacer>

                <v-btn 
					text 
					class="cabecalho_menu"
				>
					Home
				</v-btn>

                <v-btn
					text 
					class="cabecalho_menu"
				>
					Produtos
				</v-btn>
                
				<v-btn
					text 
					class="cabecalho_menu"
				>
					Preços
				</v-btn>

                <v-btn
					text 
					class="cabecalho_menu"
				>
					Sobre
				</v-btn>

                <v-btn
					text 
					class="cabecalho_menu"
				>
					Contato
				</v-btn>

            </v-app-bar>

            <v-main>
                <v-container 
					class="topo_home"
                    fluid
                    >
                    <div class="caixa_redes"
					>
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
							color="#AB2B2D"
							dark
							width="200"
							large
							>
							Saiba Mais
						</v-btn>
					</div>
                </v-container>

                <div class="py-1"></div>

				<v-container
					class="recursos"
                    fluid
				>
                    <div class="letra_titulos">
                        Recursos
                    </div>
                    <div class="letra_titulos2">
                        Descubra as vantagens das ferramentas disponíveis<br>dos sistemas AutoM
                    </div>
                </v-container>

                <div class="py-8"></div>

                <v-container
                    class="text-center"
                >

                    <v-row>
                        <v-col
                            v-for="({ src, text, title }, i) in articles"
                            :key="i"
                            cols="12"
                            md="4"
                            >
                            <v-img
                                :src="src"
                                class="mb-4"
                                height="40px"
                                width="40px"
                                max-width="100%" 
                            ></v-img>

                            <h3
                                class="font-weight-black mb-4 text-uppercase"
                                v-text="title"
                            ></h3>

                            <div
                                class="title font-weight-light mb-5"
                                v-text="text"
                            ></div>

                        </v-col>
                    </v-row>
				</v-container>
                
                <div class="py-8"></div>

                <v-container>
                    <div>
					<v-img src="src/img/screen.png"></v-img>
                    </div>
                </v-container>

                <div class="py-8"></div>

                <v-container>


                </v-container>
					<v-row no-gutters>
						<v-col
						sm="6"
						md="5"
						lg="6"
						>
						<v-card
							class="pa-2"
							tile
						>
							.col-sm-6 .col-md-5 .col-lg-6
						</v-card>
						</v-col>
						<v-col
						sm="6"
						md="5"
						offset-md="2"
						lg="6"
						offset-lg="0"
						>
						<v-card
							class="pa-2"
							tile
						>
						<div>
							A melhor maneira para <br> expandir seu negócio
						</div>

						</v-card>
						</v-col>
					</v-row>

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
        articles: [
            {
            src: 'src/img/Vector1.png',
            title: 'Campanhas automáticas',
            text: 'Com o sistema de agendamento é possível programar campanhas automáticas para envio de conteúdo para seus clientes.',
            },
            {
            src: 'src/img/Vector1.png',
            title: 'Controle de dados',
            text: 'Obtenha estatísticas do seu público e crie campanhas específicas para cada grupo',
            },
            {
            src: 'src/img/Vector2.png',
            title: 'Conteúdo personalizável',
            text: 'Os serviços AutoM possibilitam criar modelos totalmente personalizáveis',
            },
        ]
    }),
};
</script>