<script setup>
import {ref} from "vue"
import srcQuiz from "./data/quiz.json";

const quiz = ref(srcQuiz)
console.log(quiz)
</script>

<template>
  <main>
    <div class="container max-w-[900px] mx-auto flex flex-col gap-10 mt-10 px-4">
      <header class="flex gap-3">
        <h1 id="title" class="font-bold">QUIZ VUE</h1>
        <input type="text" name="" id="search-input" class="border text-md border-gray-500 rounded-md bg-gray-300">
      </header>
      <section class="grid grid-cols-3 ">
        <div class="border rounded-xl shadow-sm m-2" v-for="item in quiz" :key="item.id">
          <div class="flex flex-col">
            <img class="size-full rounded-t-xl" :src="item.img" alt="">
            <div class="flex flex-col gap-2 m-2 mt">
              <h5 class="text-md font-bold overflow-hidden">{{ item.title }}</h5>
              <p class="text-sm overflow-hidden mb-1">2 questions</p>
            </div>
          </div>
        </div>
      </section>
    </div>
  </main>
</template>