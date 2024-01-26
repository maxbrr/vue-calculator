<script setup lang="ts">
import { ref } from 'vue';
const emit = defineEmits(['buttonClick']);

const lastButtonWasOperator = ref<boolean>(true);

const handleButtonClick = (payload: string) => {
  if(lastButtonWasOperator.value && isNaN(Number(payload))) {
    console.log("operators may not follow operators")
    return;
  } else {
    if(isNaN(Number(payload))) {
      lastButtonWasOperator.value = true;
      emit('buttonClick', payload);
      console.log("Operator button clicked => " + payload);
    } else {
      lastButtonWasOperator.value = false;
      emit('buttonClick', payload);  
      console.log("Number button clicked => " + payload);
    }
  }
}
</script>

<template>
  <div id="calculator-buttons">
    <button @click="handleButtonClick('7')">7</button>
    <button @click="handleButtonClick('8')">8</button>
    <button @click="handleButtonClick('9')">9</button>
    <button @click="handleButtonClick('*')">*</button>
    <button @click="handleButtonClick('4')">4</button>
    <button @click="handleButtonClick('5')">5</button>
    <button @click="handleButtonClick('6')">6</button>
    <button @click="handleButtonClick('/')">/</button>
    <button @click="handleButtonClick('1')">1</button>
    <button @click="handleButtonClick('2')">2</button>
    <button @click="handleButtonClick('3')">3</button>
    <button @click="handleButtonClick('-')">-</button>
    <button @click="handleButtonClick('C')">C</button>
    <button @click="handleButtonClick('0')">0</button>
    <button @click="handleButtonClick('=')">=</button>
    <button @click="handleButtonClick('+')">+</button>
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
