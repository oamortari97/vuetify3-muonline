<template>
  <v-card class="mb-4">
    <v-card-title class="d-flex align-center card-title">
      <v-icon color="amber-darken-1" size="18" class="mr-2">mdi-server-outline</v-icon>
      Dados do Servidor
    </v-card-title>
    <v-card-text>
      <v-list density="compact" bg-color="transparent">

        <v-list-item>
          <template v-slot:prepend>
            <div class="text-caption text-uppercase">VERSÃO</div>
          </template>
          <template v-slot:append>
            <div class="primary--text">1.07 SEASON 16.1</div>
          </template>
        </v-list-item>

        <v-list-item>
          <template v-slot:prepend>
            <div class="text-caption text-uppercase">EXPERIÊNCIA</div>
          </template>
          <template v-slot:append>
            <div class="primary--text">20x</div>
          </template>
        </v-list-item>

        <v-list-item>
          <template v-slot:prepend>
            <div class="text-caption text-uppercase">DROP ITEMS</div>
          </template>
          <template v-slot:append>
            <div class="primary--text">30x</div>
          </template>
        </v-list-item>

        <v-list-item>
          <template v-slot:prepend>
            <div class="text-caption text-uppercase">MAX LEVEL</div>
          </template>
          <template v-slot:append>
            <div class="primary--text">400</div>
          </template>
        </v-list-item>

        <v-list-item>
          <template v-slot:prepend>
            <div class="text-caption text-uppercase">PONTOS (MÚLTIPLOS/RESET)</div>
          </template>
          <template v-slot:append>
            <div class="primary--text">5:1</div>
          </template>
        </v-list-item>

        <v-list-item>
          <template v-slot:prepend>
            <div class="text-caption text-uppercase">PONTOS (BÔNUS)</div>
          </template>
          <template v-slot:append>
            <div class="primary--text">5:1</div>
          </template>
        </v-list-item>

      </v-list>

    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'ServerData'
}
</script>
