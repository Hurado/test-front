<template>
  <h1>HelloWorld</h1>
</template>

<script lang="ts">
import { ref, computed } from "vue";

const questions = ref({
  question: "What is VueJS?",
  answer: 0,
  options: [
    "A framework JS",
    "A library JS",
    "Extension for JS",
    "Another Language"
  ]
});
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Roboto", sans-serif;
}

body {
  background-color: #271c36;
  color: #fff;
}
</style>
