<template>
  <section class="card__content">
    <base-card>
      <base-button @click="setCmp('learning-resources')"
        >Stored Resources</base-button
      >
      <base-button @click="setCmp('add-resource')">Add Resource</base-button>
      <keep-alive>
        <component :is="cmp"></component>
      </keep-alive>
    </base-card>
  </section>
</template>

<script>
import BaseCard from "./BaseCard.vue";
import BaseButton from "./BaseButton.vue";

import AddResource from "./AddResource.vue";
import LearningResources from "./LearningResources.vue";

export default {
  name: "Tabs",
  components: {
    BaseButton,
    BaseCard,
    AddResource,
    LearningResources,
  },
  data() {
    return {
      cmp: "learning-resources",
      cards: [
        {
          id: 1,
          title: "Official Guide",
          description: "the official  Vue js  documentation",
          link: "https://www.vuejs.org",
        },
        {
          id: 2,
          title: "Google",
          description: "learn how to  use google",
          link: "https://www.google.it",
        },
      ],
    };
  },
  provide() {
    return {
      resources: this.cards,
      addResource: this.addRsrc,
      removeResource: this.removeRsrc,
    };
  },

  methods: {
    setCmp(cmp) {
      this.cmp = cmp;
    },
    addRsrc(title, description, link) {
      console.log("sono il clic del tab!");
      const newCard = {
        title: title,
        description: description,
        link: link,
      };
      this.cards.push(newCard);
      console.log(newCard);
    },
    removeRsrc(cardId) {
      console.log(cardId)
    //  this.cards = this.cards.filter(card => card.id !== cardId)
    //  console.log(this.cards)
    const resIndex = this.cards.findIndex(card => card.id === cardId)
    this.cards.splice(resIndex, 1) //not working with filter because that method creates a new array which Vue is not notified of
    }
  },
};
</script>

<style scoped>
.card__content {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>