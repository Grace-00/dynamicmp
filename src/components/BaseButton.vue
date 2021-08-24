<template>
<button :class="btnAddResource">
    <slot></slot>
</button>
</template>

<script>
export default {
    name: 'Base Button',
    props: ['btnAddResource'],


}
</script>

<style scoped>
button {
    padding: 10px;
    margin-left: 20px;
    color: purple;
    cursor: pointer;
    background: transparent;
    font-size: 1rem;
}

button:hover {
    color:white;
    background-color: purple;
}

.btnAddResourceMargin {
    margin-left: 200px;
   
}
</style>