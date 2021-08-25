<template>
  <header>
    <h1>{{hdr}}</h1>

  </header>
</template>

<script>
export default {
  name: 'header',
  props: {
    hdr: {
      type: String,
      required: true,

    }
  }
}
</script>


<style scoped>
header {
  width: 100%;
  text-align: center;
  color: white;
  background-color: crimson;
  font-size: 1.5rem;
  padding: 20px 0 20px 0;
}
</style>
