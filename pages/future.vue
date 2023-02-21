<script setup lang="ts">
const months = ["february", "march", "april", "may", "june"];
const items = [
  {
    month: "february",
    logs: [
      "update future log ui to match daily log",
      "make monthly log ui",
      "start refactoring",
    ],
  },
];
</script>

<template>
  <section class="h-screen">
    <div class="mx-6 py-10">
      <h1 class="text-6xl tracking-tight">future</h1>
    </div>
    <div
      v-for="month in months"
      :key="month"
      class="mx-6 my-2 border-2 border-neutral-600 py-2"
    >
      <h1 class="px-4">{{ month }} 2023</h1>
      <div v-for="item in items" :key="item.month">
        <div v-if="month === item.month" class="py-2">
          <div v-for="log in item.logs" :key="log" class="flex gap-4 px-4">
            <div>x</div>
            <div>{{ log }}</div>
          </div>
        </div>
      </div>
    </div>
    <div class="mx-6 my-20 flex flex-col gap-2">
      <button class="bg-neutral-100 border-2 border-neutral-800 w-full py-1.5">
        select date
      </button>
    </div>
  </section>
</template>
