<template>
  <section class="card__content">
    <base-card>
      <form>
        <div class="title">
          <label for="title">Title<input type="text" v-model="title" /></label>
        </div>
        <div class="description">
          <label for="description"
            >Description<input type="text" v-model="description"
          /></label>
        </div>
        <div class="link">
          <label for="link">Link<input type="text" v-model="link" /></label>
        </div>
      </form>
      <base-button @click="addRes" btnAddResource="btnAddResourceMargin"
        >Add Resource</base-button
      >
    </base-card>
  </section>
</template>

<script>
import BaseButton from "./BaseButton.vue";
import BaseCard from "./BaseCard.vue";
export default {
  name: "AddResource",
  emits: ["addRes"],
  components: {
    BaseButton,
    BaseCard,
  },
  data() {
    return {
      title: "",
      description: "",
      link: "",
    };
  },
  inject: ['addResource'],
  methods: {
    addRes() {
        console.log('mi hai clicccato!')
        this.addResource(this.title, this.description, this.link)
    //   this.$emit("addRes", this.title, this.description, this.link);
    },
  },
};
</script>

<style scoped>
label {
  display: flex;
  justify-content: flex-end;
  text-align: right;
  width: 400px;
  line-height: 78px;
  margin-bottom: 10px;
  font-weight: bold;
}

input {
  border: 1px solid gray;

  height: 20px;
  flex: 0 0 200px;
  margin-top: 20px;
  margin-left: 10px;
  padding: 15px;
}
</style>