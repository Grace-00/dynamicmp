<template>
  
  <stored-resources
    v-for="card in resources"
    :key="card.id"
    :card="card"
   
  ></stored-resources>
</template>

<script>
import storedResources from './storedResources.vue';
export default {
  name: 'LearningResources',
  inject: ['resources'],
  components: {
    storedResources,
  },
//   methods: {
//     dlt(cardId) {
//         console.log(cardId)
//       this.cards = this.cards.filter((card) => cardId !== card.id);
//     },
//   },
};
</script>

<style scoped>
</style>