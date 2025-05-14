<template>
  <v-container class="mb-5" max-width="630px">
    <h1 class="text-center mb-6">Le Monde Pokémon</h1>

    <v-dialog>
      <template #activator="{ props: activatorProps }">
        <v-img
          v-bind="activatorProps"
          class="mb-6 map-pokemon"
          src="/images/pokemon-map.png"
        />
      </template>

      <template #default="{ isActive }">
        <v-card>
          <v-img class="w-100" src="/images/pokemon-map.png" />

          <v-card-actions>
            <v-spacer />

            <v-btn
              class="primary btn-blue-text "
              text="Fermer"
              @click="isActive.value = false"
            />
          </v-card-actions>
        </v-card>
      </template>
    </v-dialog>

    <v-card class="mx-auto">
      <v-card-text>
        <v-card-title><h2 class="text-h5 mb-1">Un univers fascinant à découvrir</h2></v-card-title>
        <v-card-text>
          <p>Le monde Pokémon est un vaste et merveilleux univers peuplé de créatures extraordinaires appelées Pokémon.
            Cette carte représente les différentes régions que les dresseurs peuvent explorer, chacune offrant ses propres
            défis, Pokémon uniques et aventures palpitantes.</p>
        </v-card-text>
        <v-card-title><h2 class="text-h5 mb-1">Des régions diversifiées</h2></v-card-title>
        <v-card-text>
          <p>De Kanto à Galar, en passant par Johto, Hoenn, Sinnoh, Unova, Kalos et Alola, chaque région du monde
            Pokémon possède sa propre identité, sa culture et son écosystème unique. Les paysages varient des montagnes
            enneigées aux îles tropicales, offrant une diversité incroyable d'habitats pour
            les différentes espèces de Pokémon.</p>
        </v-card-text>
        <v-card-title><h2 class="text-h5 mb-1">Un monde en constante évolution</h2></v-card-title>
        <v-card-text>
          <p>Le monde Pokémon est en perpétuelle expansion, avec de nouvelles régions, de nouvelles espèces de
            Pokémon et de nouvelles aventures qui sont régulièrement découvertes. Cette carte n'est qu'un aperçu
            d'un univers riche et en constante évolution, prêt à être exploré par les dresseurs audacieux.</p>
        </v-card-text>
        <v-card-title><h2 class="text-h5 mb-1">Un appel à l'aventure</h2></v-card-title>
        <v-card-text>
          <p>Que vous soyez un dresseur débutant ou expérimenté, le monde Pokémon vous invite à partir à l'aventure.
            Capturez de nouveaux Pokémon, affrontez des champions d'arènes, déjouez les plans des équipes malveillantes
            et devenez peut-être le prochain Maître Pokémon. L'aventure commence ici, sur cette carte,
            mais où vous mènera-t-elle ?</p>
        </v-card-text>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script setup>

</script>

<style scoped lang="sass">
.btn-blue-text
  color: rgb(33, 150, 243)
</style>
