<script setup lang="ts">
import { ref } from 'vue';

const lastButtonWasOperator = ref<boolean>(false);

const handleButtonClick = (payload) => {
  
}
</script>

<template>
  <div id="calculator-buttons">
    <button>7</button>
    <button>8</button>
    <button>9</button>
    <button>*</button>
    <button>4</button>
    <button>5</button>
    <button>6</button>
    <button>/</button>
    <button>1</button>
    <button>2</button>
    <button>3</button>
    <button>-</button>
    <button>C</button>
    <button>0</button>
    <button>=</button>
    <button>+</button>
  </div>
</template>

<style scoped>
#calculator-buttons {
  height: 80%;
  display: grid;
  grid-template-rows: repeat(4, 1fr);
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 5px;
  padding: 5px;
}
</style>
