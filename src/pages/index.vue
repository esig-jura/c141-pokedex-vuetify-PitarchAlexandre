<template>
  <!-- Conteneur principal pour structurer la disposition de la page -->
  <v-container>
    <h1 class="mb-6 text-center">Pokédex</h1>

    <v-text-field
      clearable
      label="Rechercher un Pokémon"
      prepend-icon="mdi-magnify"
    />

    <v-row>
      <!-- Exemple de colonne vide (à dupliquer plus tard avec du contenu) -->
      <v-col
        v-for="pokemon in pokemonStore.pokemons"
        :key="pokemon.id"
        cols="12"
        lg="3"
        md="4"
        sm="6"
        xl="2"
        xs="12"
      >
      <PokemonCard :pokemon="pokemon" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
// Récupérer le magasin de Pokémons
  import { usePokemonStore } from '@/stores/pokemonStore'
  const pokemonStore = usePokemonStore()

  console.log(pokemonStore)
</script>

<style lang="sass" scoped>
:deep(.mdi-heart)
  animation: heartbeat 1s ease-in-out
</style>
