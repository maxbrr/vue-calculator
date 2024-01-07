<script setup lang="ts">
import CalculatorDisplay from './CalculatorDisplay.vue';
import CalculatorButtons from './CalculatorButtons.vue';
</script>

<template>
  <div id="calculator">
    <CalculatorDisplay />
    <CalculatorButtons />
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
