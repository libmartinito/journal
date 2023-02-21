<script setup lang="ts">
const arr = [
  "develop ui for daily logs",
  "develop ui for monthly logs",
  "prepare endpoints",
  "refactor user interfaces",
  "try using pinia for state management if needed",
  "integrate ui components with endpoints",
  "add authorizaiton",
];
</script>

<template>
  <section class="h-screen">
    <div class="mx-6 py-10">
      <h1 class="text-6xl tracking-tight">daily</h1>
      <div class="px-1">02.21.23 tue</div>
    </div>
    <div class="mx-4 py-2 max-h-[50vh] overflow-auto">
      <div v-for="item in arr" :key="item" class="flex gap-4 px-6 py-2">
        <div>x</div>
        <div>{{ item }}</div>
      </div>
    </div>
    <div class="mx-6 my-10 flex flex-col gap-2">
      <button class="bg-neutral-800 text-neutral-200 w-full py-2">add</button>
      <button class="bg-neutral-100 border-2 border-neutral-800 w-full py-1.5 box-border">select day</button>
    </div>
  </section>
</template>
