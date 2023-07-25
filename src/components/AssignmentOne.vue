<template>
  <div>Name: {{ name }}</div>
  <div>Age in five years: {{ age + 5 }}</div>
  <div>Fav Number: {{ Math.random() }}</div>
  <div>image: <img :src="imgUrl" style="width: 40px" /></div>
  <div>
    <input type="text" v-model="name" disabled />
  </div>
</template>

<script setup>
import { ref } from "vue";
const name = ref("abc");
const age = 24;
const imgUrl =
  "https://images.unsplash.com/photo-1494253109108-2e30c049369b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTB8fHJhbmRvbXxlbnwwfHwwfHx8MA%3D%3D&w=1000&q=80";
</script>
