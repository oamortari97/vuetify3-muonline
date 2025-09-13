<template>
  <v-card class="mb-4">
    <v-card-title class="d-flex align-center card-title">
      <v-icon color="amber-darken-1" size="18" class="mr-2">mdi-newspaper-variant-outline</v-icon>
      Últimas Notícias
    </v-card-title>
    <v-card-text class="pa-0">

      <v-list density="compact" bg-color="transparent">

        <template v-for="(noticia, index) in props.noticias" :key="index">
          <v-list-item v-if="index < 5">
            <!-- Ativador do diálogo -->
            <v-card variant="flat" color="grey-darken-4" class="w-100 pa-2 mb-2" link
              @click="noticiaSelecionada = noticia; dialog = true">
              <div class="d-flex align-items-start">
                <div class="flex-grow-1">
                  <div class="d-flex align-center">
                    <v-icon size="small" color="grey">mdi-calendar-outline</v-icon>
                    <span class="text-caption ml-1">{{ noticia.data }}</span>
                    <v-icon size="small" color="grey" class="ml-2">mdi-account-outline</v-icon>
                    <span class="text-caption ml-1">{{ noticia.autor }}</span>
                  </div>
                  <div class="text-subtitle-2 mt-1">{{ noticia.titulo }}</div>
                </div>
                <v-btn :color="getColor(noticia.tipo)" size="small" variant="tonal" class="ml-2 text-none">
                  {{ noticia.tipo }}
                </v-btn>
              </div>
            </v-card>
          </v-list-item>
        </template>

        <v-dialog v-model="dialog" max-width="800">
          <v-card>
            <v-card-title class="text-h6">{{ noticiaSelecionada?.titulo }}</v-card-title>
            <v-card-subtitle>
              {{ noticiaSelecionada?.data }} - {{ noticiaSelecionada?.autor }}
            </v-card-subtitle>
            <v-card-text>
              <div style="white-space: pre-wrap">
                {{ noticiaSelecionada?.corpo || 'Conteúdo não disponível.' }}
              </div>
            </v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn text="Fechar" variant="flat" @click="dialog = false"></v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>

        <v-list-item v-if="props.noticias.length > 5">
          <div class="d-flex justify-center">
            <v-btn class="mx-1 text-none" variant="text" color="white">
              Ver todas
            </v-btn>
          </div>
        </v-list-item>
      </v-list>

    </v-card-text>
  </v-card>
</template>

<script setup>
import { ref } from 'vue'
const props = defineProps(['noticias'])
const getColor = (tipo) => {
  switch (tipo) {
    case 'Atualização':
      return 'amber'
    case 'Manutenção':
      return 'grey'
    case 'Evento':
      return 'error'
    case 'Notícia':
      return 'info'
    default:
      return 'grey';
  }
}

const dialog = ref(false)
const noticiaSelecionada = ref(null)
</script>
