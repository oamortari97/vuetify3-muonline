<template>
  <v-card class="mb-4">
    <v-card-title class="d-flex align-center card-title">
      <v-icon color="amber-darken-1" size="18" class="mr-2">{{ titleIcon }}</v-icon>
      {{ title }}
    </v-card-title>
    <v-card-text class="pa-0">
      <v-list density="compact" bg-color="transparent">
        <v-list-item v-for="(player, index) in players" :key="index">
          <v-card variant="flat" color="grey-darken-4" class="w-100 pa-2 mb-2">
            <div class="d-flex align-center">
              <v-avatar size="30" :color="getClassColor(index)" class="mr-2">
                <span class="text-caption">{{ index + 1 }}</span>
              </v-avatar>
              <div>
                <div class="text-body-2">{{ player.name }}</div>
                <div class="text-body-2 text-grey-darken-1">{{ player.class }}</div>
              </div>
              <v-spacer></v-spacer>
              <div class="text-h6" :class="getPointsColor(player.points)">{{ player.points }}</div>
            </div>
          </v-card>
        </v-list-item>
      </v-list>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'RankingCard',
  props: {
    title: {
      type: String,
      required: true
    },
    type: {
      type: String,
      default: 'semanal',
      validator: (value) => ['semanal', 'diario', 'mensal'].includes(value)
    }
  },
  computed: {
    titleIcon() {
      const icons = {
        'semanal': 'mdi-calendar-week',
        'diario': 'mdi-calendar-today',
        'mensal': 'mdi-calendar-month'
      };
      return icons[this.type] || 'mdi-trophy';
    },
    players() {
      // Dados simulados para cada tipo de ranking
      if (this.title === 'TOP 5 RESETS') {
        return [
          { name: 'DRAGONSLAYER', class: 'Grand Master', points: '15.420' },
          { name: 'ICEWARD', class: 'Grand Master', points: '14.890' },
          { name: 'FIREKNIGHT', class: 'High Elf', points: '14.650' }
        ];
      }

      return [
        { name: 'MYSTICMAGE', class: 'Magic Gladiator', points: '2.840' },
        { name: 'BLOODWARRIOR', class: 'Soul Master', points: '2.650' },
        { name: 'WINDRANGER', class: 'Grand Master', points: '2.480' }
      ];
    }
  },
  methods: {
    getClassColor(index) {
      if (index === 0) return 'amber';
      if (index === 1) return 'grey-lighten-1';
      if (index === 2) return 'amber-darken-4';
      return 'grey-darken-1';
    },
    getPointsColor(points) {
      return 'text-amber';
    }
  }
}
</script>
