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

            <v-app-bar app extension flat width="100%" class="cabecalho">
                <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>

                <v-avatar class="logo" tile size="70">
                    <v-img src="src/img/logo.png"></v-img>
                </v-avatar>

                <v-spacer></v-spacer>

                <v-btn text class="cabecalho_menu d-none d-sm-flex">
                    Home
                </v-btn>

                <v-btn text class="cabecalho_menu d-none d-sm-flex">
                    Produtos
                </v-btn>

                <v-btn text class="cabecalho_menu d-none d-sm-flex">
                    Preços
                </v-btn>

                <v-btn text class="cabecalho_menu d-none d-sm-flex">
                    Sobre
                </v-btn>

                <v-btn text class="cabecalho_menu d-none d-sm-flex">
                    Contato
                </v-btn>
            </v-app-bar>

            <v-main>
                <v-container class="topo_home mb-15" fluid>
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

                    <div class="letras_rectangle9_primeira white--text">
                        Alcance novos horizontes <br />
                        com o seu negócio
                    </div>

                    <div class="letras_rectangle9_segunda white--text">
                        Uma nova forma de realizar suas campanhas de Marketing
                        <br />
                        Digital para captação de clientes.
                    </div>

                    <div class="botao_saiba_mais">
                        <v-btn rounded color="#AB2B2D" dark width="200" large>
                            Saiba Mais
                        </v-btn>
                    </div>
                </v-container>

                <v-container class="recursos mb-15" fluid>
                    <div class="letra_titulos_recursos">Recursos</div>
                    <div class="letra_titulos_recursos2">
                        Descubra as vantagens das ferramentas disponíveis<br />dos
                        sistemas AutoM
                    </div>
                </v-container>

                <v-container class="text-center mb-15">
                    <v-row>
                        <v-col
                            v-for="({ src, text, title }, i) in articles"
                            :key="i"
                            cols="12"
                            md="4"
                        >
                            <div
                                class="d-flex flex-column"
                                style="align-items: center"
                            >
                                <v-img
                                    :src="src"
                                    class="mb-4"
                                    height="40px"
                                    width="40px"
                                ></v-img>

                                <h3
                                    class="
                                        font-weight-black
                                        mb-4
                                        text-uppercase
                                    "
                                    v-text="title"
                                ></h3>

                                <div
                                    class="title font-weight-light mb-5"
                                    v-text="text"
                                ></div>
                            </div>
                        </v-col>
                    </v-row>
                </v-container>

                <v-container class="mb-15">
                    <div>
                        <v-img src="src/img/screen.png"></v-img>
                    </div>
                </v-container>

                <v-container class="mb-15">
                    <v-row no-gutters>
                        <v-col sm="6" md="5" lg="6">
                            <v-card class="pa-2" tile elevation="0">
                                <v-container
                                    class="alinhamento_texto ajuste_box"
                                >
                                    <div class="letra_titulos_ferramenta">
                                        A melhor maneira para <br />
                                        expandir seu negócio
                                    </div>
                                    <div class="letra_titulos_ferramenta2">
                                        A ferramenta AutoM garante a<br />captação
                                        de novos clientes com<br />preços
                                        acessíveis
                                    </div>
                                    <div class="botao_saiba_mais2">
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
                            </v-card>
                        </v-col>

                        <v-col sm="6" md="5" lg="6">
                            <v-card class="pa-2" tile elevation="0">
                                <div class="ajuste_box">
                                    <v-img
                                        src="src/img/foto_notebook.png"
                                        max-width="400"
                                    ></v-img>
                                </div>
                            </v-card>
                        </v-col>
                    </v-row>
                </v-container>

                <v-container  class="mb-15">
                    <v-row no-gutters>
                        <v-col sm="6" md="5" lg="6">
                            <v-card class="pa-2" tile elevation="0">
                                <div class="ajuste_box">
                                    <v-img
                                        src="src/img/imagem_crie_links.png"
                                        max-width="400"
                                    ></v-img>
                                </div>
                            </v-card>
                        </v-col>

                        <v-col sm="6" md="5" lg="6">
                            <v-card class="pa-2" tile elevation="0">
                                <v-container
                                    class="alinhamento_texto2 ajuste_box"
                                >
                                    <div class="letra_titulos_ferramentapeq">
                                        <b>Na ponta dos seus dedos</b>
                                    </div>
                                    <div class="letra_titulos_ferramenta">
                                        Crie links para suas <br />
                                        redes sociais.
                                    </div>
                                    <div class="letra_titulos_ferramentapeq">
                                        Whatsapp, Instagram, Facebook e muito
                                        mais<br />
                                        em um só e-mail de contato.
                                    </div>
                                    <div class="botao_saiba_mais2">
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
                            </v-card>
                        </v-col>
                    </v-row>
                </v-container>

                <v-container>
                    <div class="letra_titulos_recursos">
                        Ferramentas Utilizadas
                    </div>
                    <div class="letra_titulos_recursos2">
                        Os sistemas AutoM utilizam as seguintes ferramentas<br />
                        para garantir a entrega dos serviços.
                    </div>
				</v-container>
					
				<v-container class="mb-15">
					<v-row>
					<v-col class="d-flex">
						<v-spacer></v-spacer>
						<v-img src="src/img/canvas.png" max-width="150"></v-img>
						<v-img src="src/img/google.png" max-width="150"></v-img>
						<v-spacer></v-spacer>
					</v-col>
					</v-row>

                    <div class="botao_saiba_mais3 mt-15">
                        <v-btn rounded color="#AB2B2D" dark width="200" large>
                            Saiba Mais
                        </v-btn>
                    </div>
				</v-container>
                
                <v-container class="recursos mb-15" fluid>
                    <div class="letra_titulos_recursos">Feedbacks</div>
                    <div>
						<v-img></v-img>
                    </div>
                    <div class="letra_titulos_recursos2">
                        "Meus lucros cresceram cerca de 36% no primeiro mês e 41% no ano<br />
                        depois que comecei a utilizar a ferramenta AutoM"
                    </div>
                    <div>
						<v-img></v-img>
                    </div>
                    <div class="botao_saiba_mais3 mt-15">
                        <v-btn rounded color="#AB2B2D" dark width="200" large>
                            Mais feedbacks
                        </v-btn>
                    </div>
                </v-container>

                <v-container class="precos mb-15">
                    <div class="letra_titulos_recursos white--text">Preços</div>
                    <div class="letra_titulos_recursos2 white--text">
                        Conheça os planos disponíveis
                    </div>
                </v-container>

                <v-container class="mb-15">
                    <div class="letra_titulos_recursos">Contate-nos</div>
                    <div class="letra_titulos_recursos2">
                        Conheça mais sobre nossos serviços e campanhas disponíveis.
                    </div>
                </v-container>

                <v-container class="precos mb-15">
                    
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
        articles: [
            {
                src: "src/img/Vector1.png",
                title: "Campanhas automáticas",
                text: "Com o sistema de agendamento é possível programar campanhas automáticas para envio de conteúdo para seus clientes.",
            },
            {
                src: "src/img/Vector2.png",
                title: "Controle de dados",
                text: "Obtenha estatísticas do seu público e crie campanhas específicas para cada grupo",
            },
            {
                src: "src/img/Vector2.png",
                title: "Conteúdo personalizável",
                text: "Os serviços AutoM possibilitam criar modelos totalmente personalizáveis",
            },
        ],
    }),
};
</script>