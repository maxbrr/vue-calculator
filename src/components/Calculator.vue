<script setup lang="ts">
import { ref } from 'vue';
import CalculatorDisplay from './CalculatorDisplay.vue';
import CalculatorButtons from './CalculatorButtons.vue';

const termString = ref<string>("");
const result = ref<string>("0");

let numberArray: number[] = [];
let termArray: any[] = [];

const handleButtonClick = (payload: string) => {
  if(isNaN(Number(payload))) {
    switch(payload) {
    case "+":
    case "-":
    case "*":
    case "/":
      termArray.push(numberArray);
      termArray.push(payload);
      numberArray = [];
      break;
    case "C":
      numberArray = [];
      termArray = [];
      break;
    case "=":
      console.log(termArray);
      break;
    }
  } else {
    numberArray.push(Number(payload));
    console.log(numberArray);
  }
}
</script>

<template>
  <div id="calculator">
    <CalculatorDisplay :term="termString" :result="result"/>
    <CalculatorButtons @buttonClick=" handleButtonClick"/>
  </div>
</template>

<style scoped>
#calculator {
  background-color: #262020;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 5px;
  width: 250px;
  height: 320px;
}
</style>
