<template>
  <!--
  Conteneur principal
    * v-container : Conteneur Vuetify pour centraliser et aligner le contenu.
  -->
  <v-container>
    <!--
    Titre principal
      * class="mb-6 text-center" :
        - mb-6 : Ajoute une marge inférieure de 6 unités.
        - text-center : Centre le texte horizontalement.
    -->
    <h1 class="mb-6 text-center">Foire Aux Questions (FAQ)</h1>

    <!--
    Panneaux d'expansion
      * v-expansion-panels : Conteneur pour regrouper plusieurs panneaux d'expansion.
    -->
    <v-expansion-panels>
      <!--
      Panneau individuel
        * v-for : Itère sur chaque élément de `faqItems` pour créer un panneau.
        * :key="i" : Fournit une clé unique basée sur l'index de l'élément pour optimiser le rendu.
      -->
      <v-expansion-panel v-for="(item, i) in faqItems" :key="i">
        <!--
        Titre du panneau
          * v-expansion-panel-title : Affiche la question dans l'en-tête cliquable du panneau.
        -->
        <v-expansion-panel-title>
          {{ item.question }}
        </v-expansion-panel-title>

        <!--
        Texte du panneau
          * v-expansion-panel-text : Contient la réponse affichée lorsque le panneau est ouvert.
        -->
        <v-expansion-panel-text>
          {{ item.answer }}
        </v-expansion-panel-text>
      </v-expansion-panel>
    </v-expansion-panels>
  </v-container>
</template>

<script setup>
// Importation de `ref` depuis Vue, permet de créer des données réactives.
  import { ref } from 'vue'

  // Tableau réactif (ref) contenant les questions et réponses.
  const faqItems = ref([
    {
      question: "Qu'est-ce qu'un Pokédex ?",
      answer: 'Un Pokédex est un dispositif électronique qui répertorie et fournit des informations sur les différentes espèces de Pokémon. Notre application est une version numérique de cet outil.',
    },
    {
      question: 'Comment puis-je ajouter un Pokémon à mes favoris ?',
      answer: "Pour ajouter un Pokémon à vos favoris, cliquez simplement sur l'icône en forme de cœur sur la carte du Pokémon. L'icône deviendra rouge pour indiquer que le Pokémon est maintenant dans vos favoris.",
    },
    {
      question: 'Pourquoi certains Pokémon ont-ils plusieurs types ?',
      answer: 'Certains Pokémon possèdent des caractéristiques de plusieurs types, ce qui se reflète dans leurs capacités et leurs faiblesses. Par exemple, Charizard est à la fois de type Feu et Vol.',
    },
    {
      question: 'Comment fonctionne la recherche de Pokémon ?',
      answer: 'Vous pouvez rechercher des Pokémon en tapant leur nom dans la barre de recherche. La liste se mettra à jour automatiquement pour afficher les Pokémon dont le nom correspond à votre recherche.',
    },
    {
      question: 'Que signifient les différentes statistiques des Pokémon ?',
      answer: "Les statistiques comme HP, Attaque, Défense et Vitesse représentent les capacités de base d'un Pokémon. HP représente les points de vie, Attaque la puissance offensive, Défense la résistance aux attaques, et Vitesse détermine l'ordre d'action en combat.",
    },
    {
      question: "L'application est-elle mise à jour régulièrement avec de nouveaux Pokémon ?",
      answer: "Oui, nous nous efforçons de maintenir notre base de données à jour avec les derniers Pokémon découverts. Cependant, la fréquence des mises à jour peut varier en fonction des nouvelles sorties de jeux et d'informations officielles.",
    },
  ])
</script>

<style scoped>
/* Ajoutez des styles personnalisés si nécessaire */
</style>
