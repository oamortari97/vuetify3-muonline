<template>
  <v-card class="mb-4">
    <v-card-title class="d-flex align-center card-title">
      <v-icon color="amber-darken-1" size="18" class="mr-2">mdi-account-group-outline</v-icon>
      Equipe
    </v-card-title>
    <v-card-text class="pa-0">
      <v-list density="compact" bg-color="transparent">
        <v-list-item>
          <template v-slot:prepend>
            <div class="text-body-2">TESTE</div>
          </template>
          <template v-slot:append>
            <v-chip color="success" size="small" class="text-none">ONLINE</v-chip>
          </template>
        </v-list-item>

        <v-list-item>
          <template v-slot:prepend>
            <div class="text-body-2">TESTE 2</div>
          </template>
          <template v-slot:append>
            <v-chip color="grey" size="small" class="text-none">OFFLINE</v-chip>
          </template>
        </v-list-item>
      </v-list>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'TeamList'
}
</script>
