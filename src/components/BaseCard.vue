<template>
<section >
    <slot></slot>
</section>

</template>

<script>
export default {
  name: 'Base Card',
  
};
</script>

<style scoped>
section {
  width: 80%;
  border: 2px solid transparent;
  margin: 50px 0 50px 0;
  box-shadow: 5px 5px 15px 5px rgba(0,0,0,0.31);
  padding: 10px;


}


</style>