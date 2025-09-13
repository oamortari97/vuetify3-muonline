<template>
  <v-app :theme="theme">

    <v-app-bar app dark elevation="4" class="px-4">
      <div class="d-flex align-center">
        <div class="logo-container">
        </div>
        <span class="text-caption text-uppercase ml-1">MU Online</span>
      </div>
      <v-spacer></v-spacer>
      <v-btn class="mx-1 text-none" variant="text" color="white">
        <v-icon left class="me-2">mdi-home-outline</v-icon>
        Início
      </v-btn>
      <v-btn class="mx-1 text-none" variant="text" color="white">
        <v-icon left class="me-2">mdi-account-plus-outline</v-icon>
        Cadastro
      </v-btn>
      <v-btn class="mx-1 text-none" variant="text" color="white">
        <v-icon left class="me-2">mdi-download-outline</v-icon>
        Downloads
      </v-btn>
    </v-app-bar>

    <v-main>
      <v-container fluid class="pa-0">
        <div class="banner-container">
          <div class="banner-content">
            <h1 class="text-h2 font-weight-bold primary--text text-center">MU Online</h1>
            <p class="text-subtitle-1 text-center">Servidor extra hard</p>
          </div>
        </div>

        <!-- Conteúdo Principal -->
        <v-container>
          <v-row>
            <!-- Coluna Esquerda -->
            <v-col cols="12" md="8">
              <!-- Servidor Principal -->

              <news-list :noticias="noticias" />
              <!-- Castle Siege -->
              <castle-siege :logo="guildLogo" />

              <!-- Últimas Notícias -->
            </v-col>

            <!-- Coluna Direita -->
            <v-col cols="12" md="4">
              <!-- Dados do Servidor -->
              <server-status />
              <server-data />

              <ranking-card title="TOP 5 RESETS" />
              <!-- Equipe -->
              <team-list />
            </v-col>
          </v-row>
        </v-container>
      </v-container>
    </v-main>

    <v-footer dark class="pa-4">
      <v-row>
        <v-col cols="12" md="4" class="d-flex align-center">
          <span class="text-h6 font-weight-bold primary--text">MU Online</span>
        </v-col>
        <v-col cols="12" md="4">
          <div class="text-center">
            <div class="text-subtitle-2 mb-2">LINKS RÁPIDOS</div>
            <v-btn variant="text" color="white" class="mx-1 text-none">INÍCIO</v-btn>
            <v-btn variant="text" color="white" class="mx-1 text-none">CADASTRO</v-btn>
            <v-btn variant="text" color="white" class="mx-1 text-none">DOWNLOADS</v-btn>
          </div>
        </v-col>
        <v-col cols="12" md="4">
          <div class="text-center">
            <div class="text-subtitle-2 mb-2">COMUNIDADE</div>
            <v-btn icon color="amber-darken-1" class="mx-2">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-youtube"
                viewBox="0 0 16 16">
                <path
                  d="M8.051 1.999h.089c.822.003 4.987.033 6.11.335a2.01 2.01 0 0 1 1.415 1.42c.101.38.172.883.22 1.402l.01.104.022.26.008.104c.065.914.073 1.77.074 1.957v.075c-.001.194-.01 1.108-.082 2.06l-.008.105-.009.104c-.05.572-.124 1.14-.235 1.558a2.01 2.01 0 0 1-1.415 1.42c-1.16.312-5.569.334-6.18.335h-.142c-.309 0-1.587-.006-2.927-.052l-.17-.006-.087-.004-.171-.007-.171-.007c-1.11-.049-2.167-.128-2.654-.26a2.01 2.01 0 0 1-1.415-1.419c-.111-.417-.185-.986-.235-1.558L.09 9.82l-.008-.104A31 31 0 0 1 0 7.68v-.123c.002-.215.01-.958.064-1.778l.007-.103.003-.052.008-.104.022-.26.01-.104c.048-.519.119-1.023.22-1.402a2.01 2.01 0 0 1 1.415-1.42c.487-.13 1.544-.21 2.654-.26l.17-.007.172-.006.086-.003.171-.007A100 100 0 0 1 7.858 2zM6.4 5.209v4.818l4.157-2.408z" />
              </svg>
            </v-btn>
            <v-btn icon color="amber-darken-1" class="mx-2">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-discord"
                viewBox="0 0 16 16">
                <path
                  d="M13.545 2.907a13.2 13.2 0 0 0-3.257-1.011.05.05 0 0 0-.052.025c-.141.25-.297.577-.406.833a12.2 12.2 0 0 0-3.658 0 8 8 0 0 0-.412-.833.05.05 0 0 0-.052-.025c-1.125.194-2.22.534-3.257 1.011a.04.04 0 0 0-.021.018C.356 6.024-.213 9.047.066 12.032q.003.022.021.037a13.3 13.3 0 0 0 3.995 2.02.05.05 0 0 0 .056-.019q.463-.63.818-1.329a.05.05 0 0 0-.01-.059l-.018-.011a9 9 0 0 1-1.248-.595.05.05 0 0 1-.02-.066l.015-.019q.127-.095.248-.195a.05.05 0 0 1 .051-.007c2.619 1.196 5.454 1.196 8.041 0a.05.05 0 0 1 .053.007q.121.1.248.195a.05.05 0 0 1-.004.085 8 8 0 0 1-1.249.594.05.05 0 0 0-.03.03.05.05 0 0 0 .003.041c.24.465.515.909.817 1.329a.05.05 0 0 0 .056.019 13.2 13.2 0 0 0 4.001-2.02.05.05 0 0 0 .021-.037c.334-3.451-.559-6.449-2.366-9.106a.03.03 0 0 0-.02-.019m-8.198 7.307c-.789 0-1.438-.724-1.438-1.612s.637-1.613 1.438-1.613c.807 0 1.45.73 1.438 1.613 0 .888-.637 1.612-1.438 1.612m5.316 0c-.788 0-1.438-.724-1.438-1.612s.637-1.613 1.438-1.613c.807 0 1.451.73 1.438 1.613 0 .888-.631 1.612-1.438 1.612" />
              </svg>
            </v-btn>
          </div>
        </v-col>
        <v-col cols="12" class="text-center mt-4">
          <span class="text-caption">© 2025 MU ONLINE. TODOS OS DIREITOS RESERVADOS.</span>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'
import GuildLogo from '@/assets/images/cs_king.png'

const guildLogo = ref(GuildLogo);

const noticias = ref([
  { titulo: 'Manutenção preventiva', autor: 'Admin', data: '07/05/2025 18:03', corpo: 'teste', tipo: 'Manutenção' },
  { titulo: 'Manutenção preventiva', autor: 'Admin', data: '07/05/2025 18:03', corpo: 'teste', tipo: 'Atualização' },
  { titulo: 'Manutenção preventiva', autor: 'Admin', data: '07/05/2025 18:03', corpo: 'teste', tipo: 'Evento' },
  { titulo: 'Manutenção preventiva', autor: 'Admin', data: '07/05/2025 18:03', corpo: 'teste', tipo: 'Notícia' },
  { titulo: 'Manutenção preventiva', autor: 'Admin', data: '07/05/2025 18:03', corpo: 'teste', tipo: 'Manutenção' },
  { titulo: 'Manutenção preventiva', autor: 'Admin', data: '07/05/2025 18:03', corpo: 'teste', tipo: 'Manutenção' },
  { titulo: 'Manutenção preventiva', autor: 'Admin', data: '07/05/2025 18:03', corpo: 'teste', tipo: 'Manutenção' },
  { titulo: 'Manutenção preventiva', autor: 'Admin', data: '07/05/2025 18:03', corpo: 'teste', tipo: 'Manutenção' },
])

</script>

<style>
* {
  font-family: 'Cinzel', serif !important;
}

.v-application {
  background: #050506 !important;
}

.logo-container {
  display: flex;
  align-items: center;
}

.banner-container {
  background-image: url('@/assets/images/banner-background.png');
  background-size: cover;
  background-position: center;
  height: 300px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.banner-container::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}

.banner-content {
  position: relative;
  z-index: 1;
  padding: 2rem;
  text-align: center;
}

.banner-content h1 {
  text-shadow: 0 0 10px rgba(212, 175, 55, 0.7);
  display: inline-block;
  padding: 0.5rem 2rem;
}

.banner-content p {
  margin-top: 1rem;
}

.v-card {
  border: 1px solid rgba(212, 175, 55, 0.3);
  background-color: #2A2A2A !important;
}

.v-card-title {
  display: flex;
  align-items: center;
  border-bottom: 1px solid rgba(212, 175, 55, 0.3);
  background-color: rgba(30, 30, 30, 0.8);
}

.card-title {
  color: #d4af37;
  font-size: 1rem;
}
</style>
