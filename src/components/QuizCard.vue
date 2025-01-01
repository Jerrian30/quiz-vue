<script setup>
const { quiz } =defineProps(["quiz"]);

</script>

<template>
     <div class="border rounded-xl shadow-sm m-2">
          <div class="flex flex-col">
            <img class="size-full rounded-t-xl" :src="quiz.img" alt="">
            <div class="flex flex-col gap-2 m-2 mt">
              <h5 class="text-md font-bold overflow-hidden">{{ quiz.title }}</h5>
              <p class="text-sm overflow-hidden mb-1">{{ quiz.questions.length }} questions</p>
            </div>
          </div>
        </div>
</template>