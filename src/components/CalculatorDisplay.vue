<script setup lang="ts">

defineProps(["term", "result"]);
</script>

<template>
  <div id="calculator-display">
    <h3 id="term">{{ term }}</h3>
    <h3 id="result">{{ result }}</h3>
  </div>
</template>

<style scoped>
#calculator-display {
  background-color: rgb(156, 182, 182);
  border: 2px solid black;
  border-radius: 2mm;
  height: 18%;
  margin-bottom: 5px;
}

#term {
  text-align: left;
  margin-left: 3px;
  margin-top: 2px;
}

#result {
  text-align: right;
  margin-right: 3px;
}
</style>
