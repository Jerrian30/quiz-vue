<script setup>
import {ref, watch} from "vue"
import srcQuiz from "./data/quiz.json";

import Card from "./components/QuizCard.vue";

const quiz = ref(srcQuiz)
const search = ref("")

watch(search, () => {
  quiz.value = srcQuiz.filter((quiz) => {
    return quiz.title.toLowerCase().includes(search.value.toLowerCase())
  });
});

</script>

<template>
  <main>
    <div class="container max-w-[900px] mx-auto flex flex-col gap-10 mt-10 px-4">
      <header class="flex gap-3">
        <h1 id="title" class="font-bold">QUIZ VUE</h1>
        <input v-model.trim="search" type="text" name="" id="search-input" class="border text-md border-gray-500 rounded-md bg-gray-300">
      </header>
      <section class="grid grid-cols-3 ">
        <Card v-for="item in quiz" :key="item.id" :quiz="item" />
      </section>
    </div>
  </main>
</template>