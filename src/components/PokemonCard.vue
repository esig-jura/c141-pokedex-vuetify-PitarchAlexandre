<template>
  <router-link class="text-decoration-none" :to="`/pokemon/${pokemon.id}`">
    <v-card class="pa-2" elevation="2">
      <v-img
        :alt="pokemon.name"
        contain
        height="200"
        :src="`/images/${pokemon.img}`"
      />
      <v-card-title class="text-h6">{{ pokemon.name }}</v-card-title>
      <v-card-subtitle>Niveau : {{ pokemon.level }}</v-card-subtitle>
      <v-card-actions>
        <v-btn
          color="red"
          :icon="pokemonStore.isFavorite(pokemon) ? 'mdi-heart' : 'mdi-heart-outline'"
          @click.prevent="pokemonStore.toggleFavorite(pokemon)"
        />
        <!-- .prevent désactive le premier niveau de clique de la carte, la route :to="`/pokemon/${pokemon.id}` -->
      </v-card-actions>
    </v-card>
  </router-link>
</template>

<script setup>
  import { usePokemonStore } from '@/stores/pokemonStore'
  const pokemonStore = usePokemonStore()

  defineProps({
    pokemon: Object,
    require: true,
  })
</script>

<style scoped>

</style>
