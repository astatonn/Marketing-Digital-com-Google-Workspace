<template>
    <v-app id="inspire">
        <!-- Sandwich esquerda -->
        <v-navigation-drawer v-model="drawer" fixed temporary>
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
                        <v-list-item-title>{{ item.title }}</v-list-item-title>
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
                    :href="`#${item.id}`"
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
        <v-app-bar fixed>
            <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>

            <v-avatar class="logo" tile size="55">
                <v-img src="src/img/logo.png"></v-img>
            </v-avatar>

            <v-spacer></v-spacer>

            <div
                class="d-none d-sm-flex"
                v-for="item in items_menu_all"
                :key="item.title"
            >
                <v-btn :href="`#${item.id}`" text>
                    {{ item.title }}
                </v-btn>
            </div>
        </v-app-bar>

        <v-main>
            <!-- Imagem tela principal -->
            <v-container class="top_home my-10" fluid id="home">
                <div
                    v-for="item in items_redes_sociais"
                    :key="item.icon"
                    class="pr-4 justify-end d-none d-sm-flex pt-1"
                >
                    <v-btn icon>
                        <v-icon color="white"> {{ item.icon }} </v-icon>
                    </v-btn>
                </div>

                <div class="d-flex">
                    <v-spacer></v-spacer>
                    <img class="logo_center" src="src/img/logo_center.png" />
                    <v-spacer></v-spacer>
                </div>

                <div>
                    <p class="letters_main_big white--text mt-1">
                        Alcance novos horizontes <br />
                        com o seu negócio
                    </p>

                    <p class="letters_main_medium white--text">
                        Uma nova forma de realizar suas campanhas de Marketing
                        <br />
                        Digital para captação de clientes.
                    </p>
                </div>

                <div class="botao_saiba_mais mt-16">
                    <v-btn rounded color="#AB2B2D" dark width="200" large>
                        Saiba Mais
                    </v-btn>
                </div>
            </v-container>

            <!-- Recursos -->
            <v-container class="color recursos my-10" fluid id="produtos">
                <h1 class="text-center">Recursos</h1>
                <h2 class="font-weight-regular text-center mt-5">
                    Descubra as vantagens das ferramentas disponíveis<br />dos
                    sistemas AutoM
                </h2>
            </v-container>

            <!-- 3 Ícones -->
            <v-container class="text-center my-10">
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
            <v-container class="my-10">
                <div>
                    <v-img src="src/img/screen.png"></v-img>
                </div>
            </v-container>

            <!-- Notebook -->
            <v-container class="my-10">
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
                                    dont_break
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
                                >A ferramenta AutoM garante a captação de novos
                                clientes com preços acessíveis</v-card-text
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
                                >Crie links para suas redes
                                sociais</v-card-title
                            >
                            <v-card-text
                                class="text-h6 title font-weight-light mb-5"
                                >Whatsapp, Instagram, Facebook e muito mais em
                                um só e-mail de contato.</v-card-text
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
            <v-container class="color my-10">
                <h1 class="text-center">Ferramentas Utilizadas</h1>
                <h2 class="font-weight-regular text-center mt-5">
                    Os sistemas AutoM utilizam as seguintes ferramentas<br />
                    para garantir a entrega dos serviços.
                </h2>

                <v-row>
                    <v-col class="d-flex mt-16">
                        <v-spacer></v-spacer>
                        <v-img src="src/img/canvas.png" max-width="150"></v-img>
                        <v-img src="src/img/google.png" max-width="150"></v-img>
                        <v-spacer></v-spacer>
                    </v-col>
                </v-row>

                <div class="botao_saiba_mais mt-10">
                    <v-btn rounded color="#AB2B2D" dark width="200" large>
                        Saiba Mais
                    </v-btn>
                </div>
            </v-container>

            <!-- Feedbacks -->
            <v-container class="color recursos my-15" fluid>
                <h1 class="text-center">Feedbacks</h1>

                <div class="d-flex justify-center py-8">
                    <v-img src="src/img/adossika.png" max-width="150"></v-img>
                </div>

                <h2 class="font-weight-regular text-center mt-5">
                    "Meus lucros cresceram cerca de 36% no primeiro mês e 41% no
                    ano<br />
                    depois que comecei a utilizar a ferramenta AutoM"
                </h2>
                <div class="d-flex justify-center py-3">
                    <v-img
                        src="src/img/imagem_declaracao_feedback.png"
                        max-width="200"
                    ></v-img>
                </div>
                <div class="botao_saiba_mais mt-10">
                    <v-btn rounded color="#AB2B2D" dark width="200" large>
                        Saiba Mais
                    </v-btn>
                </div>
            </v-container>

            <!-- Preços -->
            <v-container class="color_back_red2 my-10" id="precos">
                <h1 class="text-center white--text pt-2">Preços</h1>

                <h2 class="font-weight-regular text-center mt-5 white--text">
                    Conheça os planos disponíveis
                </h2>

                <v-row class="pa-8 justify-center">
                    <v-col md="4" cols="12">
                        <v-card
                            class="full-height rounded-lg"
                            style="height: 380px"
                        >
                            <v-card-text
                                class="
                                    full-height
                                    pa-2
                                    d-flex
                                    flex-column
                                    align-center
                                    black--text
                                "
                                style="height: 269px"
                            >
                                <h3 style="margin-top: 15px">BÁSICO</h3>
                                <h5>Conheça as campanhas habilitadas</h5>

                                <v-row class="pt-15">
                                    <v-col
                                        class="justify-center letters_main_big2"
                                        >9</v-col
                                    >
                                    <v-col> R$ Por mês </v-col>
                                </v-row>

                                <v-spacer />

                                <h5 class="font-weight-light">
                                    Datas comemorativas
                                </h5>
                                <h5 class="font-weight-light">
                                    Cupom primeiro cadastro
                                </h5>
                            </v-card-text>

                            <div class="botao_saiba_mais py-8">
                                <v-btn
                                    rounded
                                    color="#AB2B2D"
                                    dark
                                    width="90%"
                                    large
                                >
                                    Eu quero!
                                </v-btn>
                            </div>
                        </v-card>
                    </v-col>

                    <v-col md="4" cols="12">
                        <v-card
                            class="full-height red darken-4 rounded-lg"
                            style="height: 450px"
                        >
                            <v-card-text
                                class="
                                    full-height
                                    pa-2
                                    d-flex
                                    flex-column
                                    align-center
                                    white--text
                                "
                                style="height: 313px"
                            >
                                <h3 style="margin-top: 15px">INTERMEDIÁRIO</h3>
                                <h5>O mais escolhido</h5>

                                <v-row class="pt-15">
                                    <v-col
                                        class="justify-center letters_main_big2"
                                        >19</v-col
                                    >
                                    <v-col>
                                        <v-row>R$</v-row>
                                        <v-row>Por mês</v-row>
                                    </v-col>
                                </v-row>

                                <v-spacer />
                                <v-spacer />

                                <h5 class="font-weight-light">
                                    Datas comemorativas
                                </h5>
                                <h5 class="font-weight-light">
                                    Cupom primeiro cadastro
                                </h5>
                                <h5 class="font-weight-light">
                                    Cupom de aniversário
                                </h5>
                                <h5 class="font-weight-light">
                                    Modelos semi-personalizados
                                </h5>
                            </v-card-text>

                            <div class="botao_saiba_mais py-8">
                                <v-btn
                                    rounded
                                    color="white"
                                    width="90%"
                                    large
                                    class="red--text"
                                >
                                    Eu quero!
                                </v-btn>
                            </div>
                        </v-card>
                    </v-col>

                    <v-col md="4" cols="12">
                        <v-card
                            class="full-height rounded-lg"
                            style="height: 465px"
                        >
                            <v-card-text
                                class="
                                    full-height
                                    pa-2
                                    d-flex
                                    flex-column
                                    align-center
                                    black--text
                                "
                                style="height: 336px"
                            >
                                <h3 style="margin-top: 15px">PREMIUM</h3>
                                <h5>Alavanque seu crescimento</h5>

                                <v-row class="pt-15">
                                    <v-col
                                        class="justify-center letters_main_big2"
                                        >49</v-col
                                    >
                                    <v-col>
                                        <v-row>R$</v-row>
                                        <v-row>Por mês</v-row>
                                    </v-col>
                                </v-row>

                                <v-spacer />

                                <h5 class="font-weight-light">
                                    Solução totalmente personalizada
                                </h5>
                                <h5 class="font-weight-light">
                                    Página HTML para formulário
                                </h5>
                                <h5 class="font-weight-light">
                                    Modelos únicos para cada campanha
                                </h5>
                                <h5 class="font-weight-light">
                                    Atendimento com especialistas
                                </h5>
                                <h5 class="font-weight-light">
                                    Análise de dados coletados
                                </h5>
                            </v-card-text>

                            <div class="botao_saiba_mais py-14">
                                <v-btn
                                    rounded
                                    color="#AB2B2D"
                                    dark
                                    width="90%"
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
            <v-container class="my-10 pb-15" id="contato">
                <h1 class="text-center">Contate-nos</h1>
                <h2 class="color font-weight-regular text-center mt-5">
                    Conheça mais sobre nossos serviços e campanhas disponíveis.
                </h2>
                <v-row class="pt-5">
                    <v-col
                        sm="6"
                        md="6"
                        lg="6"
                        cols="12"
                        class="pa-10 justify-center"
                    >
                        <v-card elevation="2" outlined>
                            <v-list-item-title class="text-h4 py-5 text-center">
                                Contato
                            </v-list-item-title>

                            <v-sheet class="px-5">
                                <v-text-field
                                    label="Seu nome"
                                    filled
                                    rounded
                                    dense
                                />

                                <v-text-field
                                    label="Seu e-mail"
                                    filled
                                    rounded
                                    dense
                                />

                                <v-textarea
                                    label="Sua mensagem"
                                    filled
                                    rounded
                                    dense
                                />

                                <div class="botao_saiba_mais my-10">
                                    <v-btn
                                        rounded
                                        color="#AB2B2D"
                                        dark
                                        width="200"
                                        large
                                    >
                                        Enviar
                                    </v-btn>
                                </div>
                            </v-sheet>
                        </v-card>
                    </v-col>

                    <v-col
                        sm="6"
                        md="6"
                        lg="6"
                        cols="12"
                        class="pa-10 justify-center"
                    >
                        <v-img src="src/img/map.png" />

                        <v-container class="text-center">
                            <v-row
                                v-for="item in icones_contatos"
                                :key="item.title"
                                cols="12"
                                md="6"
                                class="my-5"
                            >
                                <v-col>
                                    <v-icon left color="#AB2B2D">
                                        {{ item.icon }}
                                    </v-icon>

                                    {{ item.title }}
                                </v-col>
                            </v-row>
                        </v-container>

                        <v-row>
                            <v-col class="d-flex mt-2 justify-center">
                                <div
                                    v-for="item in items_redes_sociais"
                                    :key="item.icon"
                                    class="pr-4 text-center text-wrap"
                                >
                                    <v-btn icon>
                                        <v-icon color="#AB2B2D">
                                            {{ item.icon }}
                                        </v-icon>
                                    </v-btn>
                                </div>
                            </v-col>
                        </v-row>
                    </v-col>
                </v-row>
            </v-container>
        </v-main>

        <!-- Footer -->
        <v-footer padless class="mt-5">
            <v-card flat tile width="100%" class="color_back_red2 text-center">
                <!-- Principal Footer -->
                <v-expansion-panels accordion v-model="panel" multiple dark>
                    <v-expansion-panel
                        v-for="(item, i) in items"
                        :key="i"
                        class="
                            color_back_red2
                            col-md-3 col-12
                            elevation-0
                            pt-10
                        "
                    >
                        <h3 class="d-none d-md-block py-2">
                            {{ item.name }}
                        </h3>
                        <v-expansion-panel-header class="d-md-none">
                            {{ item.name }}
                        </v-expansion-panel-header>
                        <v-expansion-panel-content class="color_back_red2">
                            <li v-for="(tag, i) in item.tags" :key="i">
                                <a
                                    :target="changeAncoraUrl(item.name)"
                                    v-bind:href="tag.url"
                                    class="white--text text-decoration-none"
                                    >{{ tag.urlname }}
                                </a>
                            </li>
                        </v-expansion-panel-content>
                    </v-expansion-panel>
                </v-expansion-panels>

                <!-- Redes sociais Footer -->
                <v-container class="d-flex justify-center">
                    <div
                        v-for="item in items_redes_sociais"
                        :key="item.icon"
                        class="pr-4 text-center"
                    >
                        <v-btn icon>
                            <v-icon color="white">
                                {{ item.icon }}
                            </v-icon>
                        </v-btn>
                    </div>
                </v-container>

                <!-- Ícones Maps e Celular Footer -->
                <v-container>
                    <v-row
                        active-class="font-weight-light"
                        v-for="item in items_footer"
                        :key="item.title"
                        cols="12"
                        md="12"
                        class="my-2 justify-center"
                    >
                        <v-col>
                            <v-icon color="white" left>
                                {{ item.icon }}
                            </v-icon>

                            {{ item.title }}
                        </v-col>
                    </v-row>
                </v-container>
            </v-card>
        </v-footer>
    </v-app>
</template>


<script>
export default {
    data: () => ({
        panel: [],
        drawer: null,
        items_login: [
            { title: "Conta", icon: "mdi-account" },
            { title: "Assinatura", icon: "mdi-cart" },
            { title: "Logout", icon: "mdi-logout" },
        ],
        items_menu_xs: [
            { title: "HOME", icon: "mdi-home", id: "home" },
            { title: "PRODUTOS", icon: "mdi-package-variant-closed", id: "produtos" },
            { title: "PREÇOS", icon: "mdi-currency-usd", id: "precos" },
            { title: "CONTATO", icon: "mdi-bullhorn", id: "contato" },
        ],
        items_menu_all: [
            { title: "Home", id: "home" },
            { title: "Produtos", id: "produtos" },
            { title: "Preços", id: "precos" },
            { title: "Contato", id: "contato" },
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
                src: "src/img/Vector3.png",
                title: "Conteúdo personalizável",
                text: "Os serviços AutoM possibilitam criar modelos totalmente personalizáveis",
            },
        ],
        icones_contatos: [
            {
                title: "R. Mal. Floriano Peixoto, 185 - Centro Histórico, Porto Alegre - RS, 90020-171",
                icon: "mdi-google-maps",
            },
            {
                title: "(51) 9 7070-7070",
                icon: "mdi-phone",
            },
            {
                title: "contato@autom.com.br",
                icon: "mdi-email",
            },
        ],
        rows: [
            {
                title: "Índice",
                children: ["Home", "Produtos", "Preço", "Contato"],
            },
            {
                title: "Privacidade",
                children: ["Termos de Uso", "Política de privacidade"],
            },
            {
                title: "Desenvolvedores",
                children: ["Filipe Padilha", "Flora Barbosa", "Lucas Lima"],
            },
        ],
        items_footer: [
            {
                title: "R. Mal. Floriano Peixoto, 185 - Centro Histórico, Porto Alegre - RS, 90020-171",
                icon: "mdi-google-maps",
            },
            { title: "(51) 9 7070-7070", icon: "mdi-cellphone" },
        ],
        items: [
            {
                name: "Índice",
                tags: [
                    {
                        urlname: "Home",
                        url: "#home",
                    },
                    {
                        urlname: "Produtos",
                        url: "#produtos",
                    },
                    {
                        urlname: "Preço",
                        url: "#precos",
                    },
                    {
                        urlname: "Contato",
                        url: "#contato",
                    },
                ],
            },
            {
                name: "Privacidade",
                tags: [
                    { urlname: "Termos de Uso", url: "" },
                    { urlname: "Política de privacidade", url: "" },
                ],
            },
            {
                name: "Desenvolvedores",
                tags: [
                    {
                        urlname: "Filipe Padilha",
                        url: "https://br.linkedin.com/in/fdapadilha",
                    },
                    {
                        urlname: "Flora Barbosa",
                        url: "https://br.linkedin.com/in/flora-barbosa-santiago-a13b5512a",
                    },
                    {
                        urlname: "Lucas Lima",
                        url: "https://br.linkedin.com/in/lucas-lima-477377a5",
                    },
                ],
            },
        ],
    }),

    beforeDestroy() {
        if (typeof window !== "undefined") {
            window.removeEventListener("resize", this.onResize, {
                passive: true,
            });
        }
    },

    mounted() {
        this.onResize();
        window.addEventListener("resize", this.onResize, { passive: true });
    },

    methods: {
        onResize() {
            if (window.innerWidth >= 960) {
                this.panel = [...Array(3).keys()].map((k, i) => i);
            } else {
                this.panel = [];
            }
        },

		changeAncoraUrl (name) {
			if (name !== "Índice"){
				return "_blank";	
			} 
			return "";
		}
    },
};
</script>