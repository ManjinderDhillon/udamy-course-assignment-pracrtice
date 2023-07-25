<template>
  <input type="text" v-model="task" />
  <button @click="addTask">Add Task</button>
  <div v-if="showValue">
    <ul>
      <li v-for="task in tasks" :Key="task.index">{{ task }}</li>
    </ul>
  </div>
  <button @click="toggle">{{ buttonCaption }}</button>
</template>
<script setup>
import { computed, ref } from "vue";

const buttonCaption = computed(() => {
  return showValue.value ? "Hide List" : "Show List";
});
const task = ref("");
const tasks = ref([]);
const showValue = ref(true);
const addTask = () => {
  tasks.value.push(task.value);
};
const toggle = () => {
  showValue.value = !showValue.value;
};
</script>
