<template>
  <button @click="addNumber(5)">AddFive</button>
  <button @click="addNumber(1)">AddOne</button>
  <div>Result: {{ result }}</div>
</template>
<script setup>
import { ref, computed, watch } from "vue";
const numValue = ref(null);
const result = computed(() => {
  if (numValue.value < 37) {
    return "Not Reached Yet";
  } else if (numValue.value > 37) {
    return "Too Much";
  } else {
    return numValue.value;
  }
});
watch(result, () => {
  setTimeout(() => {
    numValue.value = 0;
  }, 5000);
});

const addNumber = (num) => {
  numValue.value = numValue.value + num;
};
</script>
