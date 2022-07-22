<template>
  <h1>HelloWorld</h1>
</template>

<script lang="ts">
import { ref, computed } from "vue";

const questions = ref(
  {
  question: "What is VueJS?",
  answer: 0,
  options: [
    "A framework JS",
    "A library JS",
    "Extension for JS",
    "Another Language",
  ],
  selected: null
},
  {
  question: "What is Vuex?",
  answer: 2,
  options: [
    "Framework for Vue",
    "A library JS",
    "State management library",
    "Approach of writing code in Vue",
  ],
  selected: null
},
  {
  question: "What is Vite?",
  answer: 3,
  options: [
    "Newest package of node for Vue",
    "State management library",
    "A Library Vue",
    "An alternative for Webpack",
  ],
  selected: null
});

const quizCompleted = ref(false)

const currentQuestion = ref(0)
const score = computed (()=> {
  let value = 0;
  questions.value.map(q => {
    if (q.selected === q.answer) {
      value++
    }
  })
  return value
})

const getCurrentQuestion = computed(() => {
  let question = questions.value[currentQuestion.value]
  question.index = currentQuestion.value
  return question
})

const setAnswer = evt => {
  questions.value[currentQuestion.value].selected = evt.target.value
}
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
