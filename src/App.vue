<template>
    <div id="app">
        <v-app id="inspire">
            <!-- Sandwich esquerda -->
            <v-navigation-drawer v-model="drawer" absolute temporary app>
                <template v-slot:prepend>
                    <v-list-item two-line>
                        <v-list-item-avatar>
                            <img
                                src="https://tc.com.br/wp-content/uploads/2021/07/steve-jobs.jpg"
                                alt="John"
                            />
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
                        nav
                        dense
                        active-class="deep-purple--text text--accent-4"
                        v-for="item in items_login"
                        :key="item.title"
                        link
                    >
                        <v-list-item-icon>
                            <v-icon>{{ item.icon }}</v-icon>
                        </v-list-item-icon>

                        <v-list-item-content>
                            <v-list-item-title>{{
                                item.title
                            }}</v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                </v-list>

                <v-divider class="d-sm-none"></v-divider>

                <v-list class="py-4 d-sm-none">
                    <v-list-item
                        nav
                        dense
                        active-class="deep-purple--text text--accent-4"
                        v-for="item in items_menu_xs"
                        :key="item.title"
                        link
                    >
                        <v-list-item-icon>
                            <v-icon>{{ item.icon }}</v-icon>
                        </v-list-item-icon>

                        <v-list-item-content>
                            <v-list-item-title>{{
                                item.title
                            }}</v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                </v-list>
            </v-navigation-drawer>

            <!-- Menu -->
            <v-app-bar app extension flat width="100%">
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
                <v-container class="top_home mb-15" fluid>
                    <div
                        v-for="item in items_redes_sociais"
                        :key="item.icon"
                        class="pr-4 justify-end d-none d-sm-flex"
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
                        <v-btn rounded color="#AB2B2D" dark width="200" large>
                            Saiba Mais
                        </v-btn>
                    </div>
                </v-container>

                <!-- Recursos -->
                <v-container class="color recursos my-15" fluid>
                    <h1 class="text-center">Recursos</h1>
                    <h2 class="font-weight-regular text-center mt-5">
                        Descubra as vantagens das ferramentas disponíveis<br />dos
                        sistemas AutoM
                    </h2>
                </v-container>

                <!-- 3 Ícones -->
                <v-container class="text-center">
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
                                    class="font-weight-black text-uppercase"
                                    v-text="title"
                                ></h3>

                                <div
                                    class="color title font-weight-regular mb-5"
                                    v-text="text"
                                ></div>
                            </div>
                        </v-col>
                    </v-row>
                </v-container>

                <!-- Imagem mulher -->
                <v-container class="my-15">
                    <div>
                        <v-img src="src/img/screen.png"></v-img>
                    </div>
                </v-container>

                <!-- Notebook -->
                <v-container>
                    <v-row no-gutters>
                        <v-col
                            sm="6"
                            md="5"
                            lg="6"
                            cols="12"
                            class="d-flex justify-center"
                        >
                            <v-card class="py-15 elevation-0" max-width="75%">
                                <v-card-title
                                    class="
                                        text-h4
                                        title
                                        font-weight-normal
                                        text-wrap
                                    "
                                    >A melhor maneira para expandir seu
                                    negócio</v-card-title
                                >
                                <v-card-text
                                    class="
                                        text-h6
                                        title
                                        font-weight-light
                                        mb-5
                                        text-wrap
                                    "
                                    >A ferramenta AutoM garante a captação de
                                    novos clientes com preços
                                    acessíveis</v-card-text
                                >
                                <v-card-actions class="justify-center">
                                    <v-btn
                                        rounded
                                        color="#AB2B2D"
                                        dark
                                        width="200"
                                        large
                                        class="botao_saiba_mais mt-8"
                                    >
                                        Saiba Mais
                                    </v-btn>
                                </v-card-actions>
                            </v-card>
                        </v-col>
                        <v-col
                            cols="12"
                            sm="6"
                            md="5"
                            lg="6"
                            class="d-flex justify-center align-center"
                        >
                            <v-img
                                src="src/img/foto_notebook.png"
                                max-width="400"
                            ></v-img>
                        </v-col>
                    </v-row>

                    <!-- Crie links -->
                    <v-row>
                        <v-col
                            sm="6"
                            md="5"
                            lg="6"
                            cols="12"
                            class="d-flex justify-center align-center"
                        >
                            <v-img
                                src="src/img/imagem_crie_links.png"
                                max-width="400"
                            ></v-img>
                        </v-col>
                        <v-col
                            sm="6"
                            md="5"
                            lg="6"
                            cols="12"
                            class="d-flex justify-center"
                        >
                            <v-card class="py-15 elevation-0" max-width="70%">
                                <v-card-title
                                    class="text-h4 title font-weight-normal"
                                    >A melhor maneira para expandir seu
                                    negócio</v-card-title
                                >
                                <v-card-text
                                    class="text-h6 title font-weight-light mb-5"
                                    >A ferramenta AutoM garante a captação de
                                    novos clientes com preços
                                    acessíveis</v-card-text
                                >
                                <v-card-actions class="justify-center">
                                    <v-btn
                                        rounded
                                        color="#AB2B2D"
                                        dark
                                        width="200"
                                        large
                                        class="botao_saiba_mais mt-8"
                                    >
                                        Saiba Mais
                                    </v-btn>
                                </v-card-actions>
                            </v-card>
                        </v-col>
                    </v-row>
                </v-container>

                <!-- Ferramentas Utilizadas -->
                <v-container class="color my-15">
                    <h1 class="text-center">Ferramentas Utilizadas</h1>
                    <h2 class="font-weight-regular text-center mt-5">
                        Os sistemas AutoM utilizam as seguintes ferramentas<br />
                        para garantir a entrega dos serviços.
                    </h2>

                    <v-row>
                        <v-col class="d-flex mt-16">
                            <v-spacer></v-spacer>
                            <v-img
                                src="src/img/canvas.png"
                                max-width="150"
                            ></v-img>
                            <v-img
                                src="src/img/google.png"
                                max-width="150"
                            ></v-img>
                            <v-spacer></v-spacer>
                        </v-col>
                    </v-row>

                    <div class="botao_saiba_mais mt-16">
                        <v-btn rounded color="#AB2B2D" dark width="200" large>
                            Saiba Mais
                        </v-btn>
                    </div>
                </v-container>

                <!-- Feedbacks -->
                <v-container class="color recursos my-15" fluid>
                    <h1 class="text-center">Feedbacks</h1>

                    <div class="d-flex justify-center py-8">
                        <v-img
                            src="src/img/adossika.png"
                            max-width="150"
                        ></v-img>
                    </div>

                    <h2 class="font-weight-regular text-center mt-5">
                        "Meus lucros cresceram cerca de 36% no primeiro mês e
                        41% no ano<br />
                        depois que comecei a utilizar a ferramenta AutoM"
                    </h2>
                    <div class="d-flex justify-center py-8">
                        <v-img
                            src="src/img/imagem_declaracao_feedback.png"
                            max-width="200"
                        ></v-img>
                    </div>
                    <div class="botao_saiba_mais mt-16">
                        <v-btn rounded color="#AB2B2D" dark width="200" large>
                            Saiba Mais
                        </v-btn>
                    </div>
                </v-container>

                <!-- Preços -->
                <v-container class="color_back_red">
                    <h1 class="text-center white--text">Preços</h1>
                    <h2
                        class="font-weight-regular text-center mt-5 white--text"
                    >
                        Conheça os planos disponíveis
                    </h2>

                    <v-row class="pa-16 justify-center">
                        <v-col cols="3" class="">
                            <v-card class="full-height rounded-lg ">
                                <v-card-text
                                    class="
                                        full-height
                                        pa-2
                                        d-flex
                                        flex-column
                                        align-center
                                        black--text
                                    "
                                >
                                    <h3 class="">BÁSICO</h3>
                                    <h5 class="">
                                        Conheça as campanhas habilitadas
                                    </h5>

                                    <v-row class="">
                                        <v-col class="letters_main_big2">9</v-col>
                                        <v-col> R$ Por mês </v-col>
                                    </v-row>

                                    <v-spacer />

                                    <h5 class=" font-weight-light">
                                        Datas comemorativas
                                    </h5>
                                    <h5 class="font-weight-light">
                                        Cupom primeiro cadastro
                                    </h5>
                                </v-card-text>

                                <div class="botao_saiba_mais">
                                    <v-btn
                                        rounded
                                        color="#AB2B2D"
                                        dark
                                        width="200"
                                        large
                                    >
                                        Eu quero!
                                    </v-btn>
                                </div>
                            </v-card>
                        </v-col>

                        <v-col cols="3">
                            <v-card class="full-height red darken-4 rounded-lg">
                                <v-card-text
                                    class="
                                        full-height
                                        pa-2
                                        d-flex
                                        flex-column
                                        align-center
                                        white--text
                                    "
                                >
                                    <h3 class="">INTERMEDIÁRIO</h3>
                                    <h5 class="">O mais escolhido</h5>

                                    <v-row class="">
                                        <v-col
                                            class="justify-end letters_main_big2">19</v-col
                                        >
                                        <v-col>
                                            <v-row>R$</v-row>
                                            <v-row>Por mês</v-row>
                                        </v-col>
                                    </v-row>

                                    <v-spacer />

                                    <h5 class=" font-weight-light">
                                        Datas comemorativas
                                    </h5>
                                    <h5 class=" font-weight-light">
                                        Cupom primeiro cadastro
                                    </h5>
                                    <h5 class=" font-weight-light">
                                        Cupom de aniversário
                                    </h5>
                                    <h5 class=" font-weight-light">
                                        Modelos semi-personalizados
                                    </h5>
                                </v-card-text>

                                <div class="botao_saiba_mais ">
                                    <v-btn
                                        rounded
                                        color="white"
                                        width="200"
                                        large
                                        class="red--text"
                                    >
                                        Eu quero!
                                    </v-btn>
                                </div>
                            </v-card>
                        </v-col>

                        <v-col cols="3" class="">
                            <v-card class="full-height rounded-lg">
                                <v-card-text
                                    class="
                                        full-height
                                        pa-2
                                        d-flex
                                        flex-column
                                        align-center
                                        black--text
                                    "
                                >
                                    <h3 class="">PREMIUM</h3>
                                    <h5 class="">
                                        Alavanque seu crescimento
                                    </h5>

                                    <v-row class="">
                                        <v-col
                                            class="justify-end letters_main_big2">49</v-col
                                        >
                                        <v-col>
                                            <v-row>R$</v-row>
                                            <v-row>Por mês</v-row>
                                        </v-col>
                                    </v-row>

                                    <v-spacer />

                                    <h5 class=" font-weight-light">
                                        Solução totalmente personalizada
                                    </h5>
                                    <h5 class=" font-weight-light">
                                        Página HTML para formulário
                                    </h5>
                                    <h5 class=" font-weight-light">
                                        Modelos únicos para cada campanha
                                    </h5>
                                    <h5 class=" font-weight-light">
                                        Atendimento com especialistas
                                    </h5>
                                    <h5 class=" font-weight-light">
                                        Análise de dados coletados
                                    </h5>
                                </v-card-text>

                                <div class="botao_saiba_mais py-4">
                                    <v-btn
                                        rounded
                                        color="#AB2B2D"
                                        dark
                                        width="200"
                                        large
                                    >
                                        Eu quero!
                                    </v-btn>
                                </div>
                            </v-card>
                        </v-col>
                    </v-row>
                </v-container>

                <!-- Contate -->
                <v-container class="color my-15">
                    <h1 class="text-center">Contate-nos</h1>
                    <h2 class="font-weight-regular text-center mt-5">
                        Conheça mais sobre nossos serviços e campanhas
                        disponíveis.
                    </h2>
                </v-container>
            </v-main>

            <!-- Footer -->
            <footer>
                <v-container class="color_back_red my-15">
                    <v-row>
                        <v-col cols="12" md="4">
                            <v-list-item
                                v-for="item in footer_names"
                                :key="item.title"
                                class="white--text d-flex flex-column"
                            >
                                <v-list-item-icon>
                                    <v-list-item-title
                                        class="font-weight-bold"
                                        >{{ item.title }}</v-list-item-title
                                    >
                                </v-list-item-icon>

        
                                <v-list-item-content>
                                    <v-list-item-title 
                  v-for="sub in item.sub_menu"
                  :key="sub.title"
                  ><a href="">{{sub.text}}</a></v-list-item-title>
                                </v-list-item-content>
                            </v-list-item>
                        </v-col>
                    </v-row>
                </v-container>
            </footer>
        </v-app>
    </div>
</template>


<script>
export default {
    data: () => ({
        drawer: null,
        items_login: [
            { title: "Conta", icon: "mdi-account" },
            { title: "Assinatura", icon: "mdi-cart" },
            { title: "Logout", icon: "mdi-logout" },
        ],
        items_menu_xs: [
            { title: "PRODUTOS", icon: "mdi-package-variant-closed" },
            { title: "PREÇOS", icon: "mdi-currency-usd" },
            { title: "SOBRE", icon: "mdi-information-outline" },
            { title: "CONTATO", icon: "mdi-bullhorn" },
        ],
        items_menu_all: [
            { title: "Home" },
            { title: "Produtos" },
            { title: "Preços" },
            { title: "Sobre" },
            { title: "Contato" },
        ],
        items_redes_sociais: [
            { icon: "mdi-twitter" },
            { icon: "mdi-facebook" },
            { icon: "mdi-linkedin" },
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
        footer_names: [
            {
                title: "Índice",
                sub_menu: [
                    { text: "Home" },
                    { text: "Produtos" },
                    { text: "Preço" },
                    { text: "Sobre" },
                    { text: "Contato" },
                ],
            },
        ],
    }),
};
</script>