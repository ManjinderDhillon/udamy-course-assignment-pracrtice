<template>
  <p :class="applyClass">Stye me</p>
  <input type="text" v-model="inputClass" />
  <div>
    <button @click="toggle">Toggle</button>
  </div>
  <div>
    <input
      type="text"
      placeholder="Set Background Color"
      v-model="backgroundValue"
    />
  </div>
  <div :style="{ backgroundColor: backgroundValue }">
    Set Background color by input field
  </div>
</template>
<script setup>
import { ref, computed } from "vue";
const inputClass = ref(null);
const peraVisible = ref(true);
const backgroundValue = ref("");
const applyClass = computed(() => {
  return {
    user1: inputClass.value === "user1",
    user2: inputClass.value === "user2",
    show: peraVisible.value,
    hide: !peraVisible.value,
  };
});
const toggle = () => {
  peraVisible.value = !peraVisible.value;
  console.log(peraVisible.value);
};
</script>
<style scoped>
p {
  border: 1px solid;
  width: 60px;
  padding: 4px;
}
.user1 {
  background-color: red;
  color: white;
}
.user2 {
  background-color: green;
  color: white;
}
.hide {
  display: none;
}
.show {
  display: block;
}
</style>
