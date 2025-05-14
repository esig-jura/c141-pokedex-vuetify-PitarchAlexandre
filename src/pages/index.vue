<template>
  <!-- Conteneur principal pour structurer la disposition de la page -->
  <v-container>
    <h1 class="mb-6 text-center">
      Pokédex

      <!--
      bouton pour ajouter un pokémon
        * aria-label : accessibilité pour les lecteurs d'écran
        * v-tooltip : info-bulle au survol
        * @click : navigation vers la page de création
      -->
      <v-btn
        v-tooltip.bottom="'Ajouter un Pokémon'"
        aria-label="Ajouter un Pokémon"
        class="ml-4"
        color="primary"
        icon="mdi-plus"
        @click="$router.push('pokemons/create')"
      />
    </h1>

    <v-text-field
      v-model="search"
      clearable
      label="Rechercher un Pokémon"
      prepend-icon="mdi-magnify"
    />

    <v-row>
      <!-- Exemple de colonne vide (à dupliquer plus tard avec du contenu) -->
      <v-col
        v-for="pokemon in filteredPokemons"
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
  import { computed, ref } from 'vue'
  // Récupérer le magasin de Pokémons
  import { usePokemonStore } from '@/stores/pokemonStore'
  const pokemonStore = usePokemonStore()
  const search = ref('')

  const sortedPokemons = computed(() => {
    return [...pokemonStore.pokemons].sort((a, b) =>
      a.name.localeCompare(b.name)
    )
  })

  const filteredPokemons = computed(() => {
    const query = search.value.toLowerCase().trim()
    return sortedPokemons.value.filter(pokemon =>
      pokemon.name.toLowerCase().includes(query))
  })

  console.log(pokemonStore)
</script>

<style lang="sass" scoped>
:deep(.mdi-heart)
  animation: heartbeat 1s ease-in-out
</style>
