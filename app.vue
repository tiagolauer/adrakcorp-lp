<template>
  <v-app dark>
    <v-app-bar color="red darken-4" dark flat elevate-on-scroll>
      <v-toolbar-title class="font-weight-bold">
        <v-icon left class="mr-2" color="red-accent-2" size="32">mdi-fire</v-icon>
        Adrak Corporation
      </v-toolbar-title>
      <v-spacer />
      <v-btn text href="#produtos" class="mx-2" color="red-accent-2">
        <v-icon left>mdi-briefcase-variant</v-icon>Produtos
      </v-btn>
      <v-btn text href="#sobre" class="mx-2" color="red-accent-2">
        <v-icon left>mdi-information</v-icon>Sobre
      </v-btn>
      <v-btn text href="#contato" class="mx-2" color="red-accent-2">
        <v-icon left>mdi-email</v-icon>Contato
      </v-btn>
    </v-app-bar>

    <v-main>
      <v-container class="pa-0" fluid>
        <v-row align="center" justify="center" class="hero-section">
          <v-col cols="12" md="8" class="text-center">
            <transition name="fade-slide">
              <div>
                <h1 class="display-2 font-weight-bold mb-4 text-red-accent-2">
                  Inovação em Cripto para o Futuro Financeiro
                </h1>
                <p class="subtitle-1 mb-6 text-grey-lighten-2">
                  Conheça as soluções da Adrak Corporation para pagamentos, carteiras digitais e integração blockchain.
                </p>
                <v-btn color="red accent-2" large class="elevation-12 animate-bounce" href="#produtos">
                  <v-icon left>mdi-arrow-down-bold-circle</v-icon>
                  Saiba Mais
                </v-btn>
              </div>
            </transition>
          </v-col>
        </v-row>

        <v-row id="produtos" class="my-16 justify-center">
          <v-col cols="12" class="text-center mb-8">
            <h2 class="font-weight-bold text-red-accent-2 mb-2">Nossos Projetos</h2>
            <v-divider class="mx-auto" style="width: 80px; background: #ff5252;" />
          </v-col>
          <v-col
            v-for="(produto, i) in produtos"
            :key="i"
            cols="12"
            md="4"
            class="d-flex align-stretch"
          >
            <v-hover v-slot="{ isHovering, props }">
              <v-card
                v-bind="props"
                class="mx-auto card-animate"
                elevation="isHovering ? 18 : 8"
                color="grey darken-4"
                dark
                :style="{ transform: isHovering ? 'scale(1.04)' : 'scale(1)', transition: 'transform 0.3s' }"
              >
                <v-card-title class="justify-center">
                  <v-icon size="48" color="red-accent-2" class="mb-2">{{ produto.icone }}</v-icon>
                </v-card-title>
                <v-card-subtitle class="text-h6 font-weight-bold text-red-accent-2 text-center">
                  {{ produto.titulo }}
                </v-card-subtitle>
                <v-card-text class="text-center text-grey-lighten-2">
                  {{ produto.descricao }}
                </v-card-text>
              </v-card>
            </v-hover>
          </v-col>
        </v-row>

        <v-row id="sobre" class="my-16 justify-center">
          <v-col cols="12" md="8">
            <v-sheet elevation="3" rounded class="pa-8" color="grey darken-3" dark>
              <h2 class="mb-4 font-weight-bold text-red-accent-2">
                <v-icon left color="red-accent-2">mdi-information-variant</v-icon>
                Sobre a Adrak Corporation
              </h2>
              <p class="subtitle-1 text-grey-lighten-2">
                Somos uma empresa especializada em soluções tecnológicas para o mercado de criptomoedas, oferecendo inovação, segurança e facilidade para empresas e usuários finais. Nosso foco é criar produtos que conectam o mundo cripto ao cotidiano das pessoas e negócios.
              </p>
            </v-sheet>
          </v-col>
        </v-row>

        <v-row id="contato" class="my-16 justify-center">
          <v-col cols="12" md="6">
            <v-sheet elevation="3" rounded class="pa-8 text-center" color="grey darken-3" dark>
              <h2 class="mb-4 font-weight-bold text-red-accent-2">
                <v-icon left color="red-accent-2">mdi-email-fast</v-icon>
                Fale Conosco
              </h2>
              <v-btn icon color="red-accent-2" class="mb-2">
                <v-icon size="36">mdi-email</v-icon>
              </v-btn>
              <div class="mb-4 text-grey-lighten-2">contato@adrakcorp.com</div>
              <v-btn icon color="red-accent-2" class="mb-2">
                <v-icon size="36">mdi-whatsapp</v-icon>
              </v-btn>
              <div class="mb-2 text-grey-lighten-2">(99) 99999-9999</div>
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
    </v-main>

    <v-footer color="red darken-4" dark padless>
      <v-col class="text-center py-3">&copy; 2024 Adrak Corporation. Todos os direitos reservados.</v-col>
    </v-footer>
  </v-app>
</template>

<script setup>
const produtos = [
  {
    titulo: 'Adrak Wallet',
    descricao: 'Conta de pagamentos de médio porte em Cripto para consumidores. Segurança, praticidade e integração total com o ecossistema digital.',
    icone: 'mdi-wallet'
  },
  {
    titulo: 'BitCredit',
    descricao: 'Cartão de crédito com Bitcoin como garantia (NFC cripto-native). Use seu saldo em BTC como colateral para compras no mundo real.',
    icone: 'mdi-credit-card-chip'
  },
  {
    titulo: 'Wallets Pay',
    descricao: 'Soluções de pagamento cripto para comércio local. Aceite criptomoedas com facilidade e expanda seus negócios para o futuro.',
    icone: 'mdi-cash-multiple'
  }
]
</script>

<style scoped>
.hero-section {
  min-height: 60vh;
  background: linear-gradient(135deg, #1a1a1a 60%, #b71c1c 100%);
  color: #fff;
  border-radius: 0 0 32px 32px;
  box-shadow: 0 8px 32px rgba(44, 62, 80, 0.15);
  animation: fadeIn 1.2s;
}
.text-red-accent-2 {
  color: #ff5252 !important;
}
.card-animate {
  transition: box-shadow 0.3s, transform 0.3s;
}
.fade-slide-enter-active {
  animation: fadeSlideIn 1s;
}
@keyframes fadeSlideIn {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
.animate-bounce {
  animation: bounce 1.2s infinite alternate;
}
@keyframes bounce {
  0% { transform: translateY(0);}
  100% { transform: translateY(-10px);}
}
</style>