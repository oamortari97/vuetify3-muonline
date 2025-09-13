<template>
  <v-card class="mb-4">
    <v-card-title class="d-flex align-center card-title">
      <v-icon color="amber-darken-1" size="18" class="mr-2">mdi-crown-outline</v-icon>
      Castle Siege
      <v-spacer></v-spacer>
    </v-card-title>
    <v-card-text class="pa-5">
      <v-row>
        <v-col cols="12">
          <v-row class="mb-1">
            <v-col cols="12">
              <div class="d-flex align-center justify-space-between">
                <div>
                  Próxima batalha:
                </div>
                <div class="font-weight-bold">
                  <v-btn color="amber-darken-2" size="small" variant="tonal" class="ml-2 text-none">
                    DOMINGO às 19:00
                  </v-btn>
                </div>
              </div>
            </v-col>
          </v-row>
          <v-card variant="flat" color="grey-darken-4" class="pa-2">
            <div class="d-flex align-center">
              <img :src="logo" width="99">
              <div class="pa-3">
                <div class="text-amber-darken-1 text-h5 text-uppercase mb-3">PHOENIX</div>
                <div class="text-body-2">SENHOR DO CASTELO: <span class="text-amber-darken-1">TESTE</span></div>
              </div>
              <v-spacer></v-spacer>
              <div class="d-flex flex-column align-end">
                <span class="text-uppercase text-h6">7 DIAS</span>
                <span class="text-caption">NO PODER</span>
              </div>
            </div>
          </v-card>
        </v-col>
      </v-row>

    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'CastleSiege',
  props: {
    logo: {
      type: String,
      required: true
    }
  }
}

</script>
