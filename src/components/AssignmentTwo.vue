<template>
  <div>
    <button @click="showalert">Alert</button>
  </div>
  <div>
    {{ inputValue }}
  </div>
  <div>
    <input type="text" v-on:keydown="showInput" />
  </div>
  <div>
    <input
      type="text"
      v-on:keydown="showInput"
      v-on:keyup.enter="confirmInput"
    />
  </div>
  <div>{{ secondInputValue }}</div>
</template>
<script setup>
import { ref } from "vue";

const inputValue = ref(null);
const secondInputValue = ref(null);
const showalert = () => {
  alert("Button Pressed");
};
const showInput = (event) => {
  inputValue.value = event.target.value;
};
const confirmInput = () => {
  secondInputValue.value = inputValue.value;
};
</script>
