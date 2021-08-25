<template>
  <section class="card__content">
    <base-card>
      <h2>{{ card.title }}</h2>
      <h3>{{ card.description }}</h3>
      <a :href="card.link" target="_blank">View Resource</a>

      <base-button @click="removeResource(card.id)">Delete</base-button>
    </base-card>
  </section>
</template>

<script>
import BaseCard from './BaseCard.vue';
import BaseButton from './BaseButton.vue';
export default {
  name: 'storedResources',
  components: {
    BaseCard,
    BaseButton,
  },
  props: {
    card: {
      type: Object,
      required: true,
    },
  },
 inject: ['removeResource'],
};
</script>

<style scoped>
a {
  color: orange;
  text-decoration: none;
}

h3 {
  margin-top: 20px;
}

.card__content {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>