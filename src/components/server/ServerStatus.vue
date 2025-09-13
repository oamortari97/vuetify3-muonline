<template>
  <v-card class="mb-4">
    <v-card-title class="d-flex align-center card-title">
      <v-icon color="success" size="18" class="mr-2">mdi-circle-outline</v-icon>
      Servidor Principal
      <v-chip color="success" size="small" class="ml-2">ONLINE</v-chip>
    </v-card-title>
    <v-card-text class="pa-4">
      <v-row>
        <v-col cols="12">
          <div class="d-flex flex-column align-center">
            <v-btn color="amber-darken-2" size="small" variant="tonal" class="mb-1 text-h5">
              150
            </v-btn>
            <div class="text-caption text-uppercase">JOGADORES ONLINE</div>
          </div>
        </v-col>
      </v-row>
      <v-row class="mt-1">
        <v-col cols="12">
          <v-progress-linear model-value="30" height="6" color="amber-darken-1" bg-color="grey-darken-3"
            rounded></v-progress-linear>
          <div class="d-flex justify-space-between mt-1">
            <span class="text-caption">0</span>
            <span class="text-caption">500</span>
          </div>
        </v-col>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'ServerStatus'
}
</script>
