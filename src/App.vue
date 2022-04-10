<template>
    <div id="app">
        <v-app id="inspire">
            
            <!-- Sandwich esquerda -->
            <v-navigation-drawer 
                v-model="drawer" 
                absolute 
                temporary 
                app
            >
                <template v-slot:prepend>
                    <v-list-item 
                        two-line 
                        >
                        <v-list-item-avatar>
                            <img src="https://tc.com.br/wp-content/uploads/2021/07/steve-jobs.jpg" alt="John">
                        </v-list-item-avatar>
            
                        <v-list-item-content>
                            <v-list-item-title>José Maria</v-list-item-title>
                            <v-list-item-subtitle>Online</v-list-item-subtitle>
                        </v-list-item-content>
                    </v-list-item>
                </template>
  
                <v-divider></v-divider>

                <v-list class="py-4">
                    <v-list-item
                        nav dense
                        active-class="deep-purple--text text--accent-4"
                        v-for="item in items_login"
                        :key="item.title"
                        link
                    >
                        <v-list-item-icon>
                            <v-icon>{{ item.icon }}</v-icon>
                        </v-list-item-icon>

                        <v-list-item-content>
                            <v-list-item-title>{{ item.title }}</v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                </v-list>

                <v-divider class="d-sm-none"></v-divider>

                <v-list class="py-4 d-sm-none">
                    <v-list-item
                        nav dense
                        active-class="deep-purple--text text--accent-4"
                        v-for="item in items_menu_xs"
                        :key="item.title"
                        link
                    >
                        <v-list-item-icon>
                            <v-icon>{{ item.icon }}</v-icon>
                        </v-list-item-icon>

                        <v-list-item-content>
                            <v-list-item-title>{{ item.title }}</v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                </v-list>

            </v-navigation-drawer>

            <!-- Menu -->
            <v-app-bar
                app 
                extension 
                flat
                width="100%"
                >
                <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>

                <v-avatar class="logo" tile size="70">
                    <v-img src="src/img/logo.png"></v-img>
                </v-avatar>

                <v-spacer></v-spacer>

                <div 
                    class="d-none d-sm-flex"
                    v-for="item in items_menu_all"
                    :key="item.title"
                >
                    <v-btn text>
                        {{ item.title }}
                    </v-btn>
                </div>

            </v-app-bar>

            <v-main>
                <!-- Imagem tela principal -->
                <v-container 
                    class="top_home mb-15"
                    fluid
                    >
                    <div 
                        v-for="item in items_redes_sociais"
                        :key="item.icon"
                        class="d-flex pr-4 justify-end"
                    >
                        <v-btn icon>
                            <v-icon color="white"> {{ item.icon }} </v-icon>
                        </v-btn>
                    </div>

                    <p class="letters_main_big white--text">
                        Alcance novos horizontes <br />
                        com o seu negócio
                    </p>

                    <p class="letters_main_medium white--text">
                        Uma nova forma de realizar suas campanhas de Marketing
                        <br />
                        Digital para captação de clientes.
                    </p>

                    <div class="botao_saiba_mais mt-16">
                        <v-btn 
                            rounded color="#AB2B2D"
                            dark width="200"
                            large
                            >
                            Saiba Mais
                        </v-btn>
                    </div>
                </v-container>

                <!-- Recursos -->
                <v-container
                    class="recursos mb-15"
                    fluid
                    >
                    <h1 class=" text-center">Recursos</h1>
                    <h2 class="grey--text font-weight-regular text-center mt-5">
                        Descubra as vantagens das ferramentas disponíveis<br />dos
                        sistemas AutoM
                    </h2>
                </v-container>

                <!-- 3 Ícones -->
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

                <!-- Imagem mulher -->
                <v-container class="mb-15">
                    <div>
                        <v-img src="src/img/screen.png"></v-img>
                    </div>
                </v-container>

                <!-- Notebook + Homem -->
                <v-container class="text-center mb-15">
                    <v-row
                        v-for="({ src, text }, i) in text_img1"
                        :key="i"
                        justify="space-around"
                        style="height: 400px"
                    >
                        <v-col
                            md="4"
                        >
                            <div
                                class="d-flex flex-row"
                            >
                                <v-img
                                    :src="src"
                                    class="mb-4"
                                    max-width="400"
                                ></v-img>
                            </div>
                        </v-col>
                        <v-col
                            md="4"
                        >
                            <div
                                class="title font-weight-light mb-5"
                                v-text="text"
                            ></div>
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
                        </v-col>
                    </v-row>



                    <v-row
                        v-for="({ src, text }, i) in text_img2"
                        :key="i"
                        justify="space-around"
                        style="height: 400px"
                    >
                        <v-col
                            md="4"
                        >
                            <div
                                class="title font-weight-light mb-5"
                                v-text="text"
                            ></div>

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
                        </v-col>
                        <v-col
                            md="4"
                        >
                            <div
                                class="d-flex flex-row"
                                style="align-text: start"
                            >
                                <v-img
                                    :src="src"
                                    class="mb-4"
                                    max-width="400"

                                ></v-img>
                            </div>

                        </v-col>
                    </v-row>
                </v-container>

                <!-- Ferramentas Utilizadas -->
                <v-container>
                    <div class="letra_titulos_recursos">
                        Ferramentas Utilizadas
                    </div>
                    <div class="letra_titulos_recursos2">
                        Os sistemas AutoM utilizam as seguintes ferramentas<br />
                        para garantir a entrega dos serviços.
                    </div>

                    <v-row>
					<v-col class="d-flex mt-16">
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
                
                <!-- Feedbacks -->
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

                <!-- Preços -->
                <v-container class="precos mb-15">
                    <div class="letra_titulos_recursos white--text">Preços</div>
                    <div class="letra_titulos_recursos2 white--text">
                        Conheça os planos disponíveis
                    </div>
                </v-container>

                <!-- Contate -->
                <v-container class="mb-15">
                    <div class="letra_titulos_recursos">Contate-nos</div>
                    <div class="letra_titulos_recursos2">
                        Conheça mais sobre nossos serviços e campanhas disponíveis.
                    </div>
                </v-container>

                <!-- Footer -->
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
        items_login: [
            {title:'Conta', icon:'mdi-account'},
            {title:'Assinatura', icon:'mdi-cart'},
            {title:'Logout', icon:'mdi-logout'},
        ],
        items_menu_xs: [
            {title:'PRODUTOS', icon:'mdi-package-variant-closed'},
            {title:'PREÇOS', icon:'mdi-currency-usd'},
            {title:'SOBRE', icon:'mdi-information-outline'},
            {title:'CONTATO', icon:'mdi-bullhorn'},
        ],
        items_menu_all: [
            {title:'Home'},
            {title:'Produtos'},
            {title:'Preços'},
            {title:'Sobre'},
            {title:'Contato'},
        ],
        items_redes_sociais: [
            {icon:'mdi-twitter'},
            {icon:'mdi-facebook'},
            {icon:'mdi-linkedin'},
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
        text_img1: [
            {
                src: "src/img/foto_notebook.png",
                text: "Com o sistema de agendamento é possível programar campanhas automáticas para envio de conteúdo para seus clientes.",
            },
        ],
        text_img2: [
            {
                src: "src/img/imagem_crie_links.png",
                text: "Obtenha estatísticas do seu público e crie campanhas específicas para cada grupo",
            },
        ],
    }),
};
</script>