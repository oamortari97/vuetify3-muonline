<template>
  <v-card class="mb-4 game-info-card">
    <v-card-title class="d-flex align-center card-title">
      <v-icon color="primary" class="mr-2">mdi-sword-cross</v-icon>
      Reino
    </v-card-title>
    <v-card-text>
      <p class="text-body-2 mb-4">
        ENTRE NA MAIOR AVENTURA MMORPG MEDIEVAL! EXPLORE DUNGEONS ÉPICAS, PARTICIPE DE BATALHAS PVP INTENSAS E CONSTRUA SUA LENDA IMORTAL.
      </p>
      
      <v-row>
        <v-col cols="6">
          <div class="d-flex align-center">
            <v-icon color="error" size="small" class="mr-2">mdi-sword</v-icon>
            <span class="text-caption text-uppercase">SEASON</span>
            <v-spacer></v-spacer>
            <span class="text-caption error--text">16.1</span>
          </div>
        </v-col>
        <v-col cols="6">
          <div class="d-flex align-center">
            <v-icon color="warning" size="small" class="mr-2">mdi-star</v-icon>
            <span class="text-caption text-uppercase">EXP RATE</span>
            <v-spacer></v-spacer>
            <span class="text-caption warning--text">20x</span>
          </div>
        </v-col>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'GameInfo'
}
</script>

<style scoped>
.game-info-card {
  border: 1px solid rgba(212, 175, 55, 0.3);
  background-color: #2A2A2A !important;
}
</style>
