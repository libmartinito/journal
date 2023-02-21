<script setup lang="ts">
const logs = [
  "finish journal side project",
  "try finishing blog api",
  "make article on how it was done",
];
const mode = ref<string>("logs");
const months = {
  feb: 28,
};
const updateMode = () => {
  mode.value === "logs" ? (mode.value = "calendar") : (mode.value = "logs");
};
const daySymbolArr = ["m", "t", "w", "t", "f", "s", "s"];
const days = computed(() => {
  const arr = [];
  for (let i = 0; i < months.feb; i++) {
    arr.push(i + 1);
  }
  return arr;
});
</script>

<template>
  <section class="h-screen">
    <div class="mx-6 py-10">
      <h1 class="text-6xl tracking-tight">monthly</h1>
      <div class="px-1">02.23 feb</div>
    </div>
    <div v-if="mode === 'logs'" class="mx-4 py-2 overflow-auto">
      <div v-for="log in logs" :key="log" class="flex gap-4 px-6 py-2">
        <div>x</div>
        <div>{{ log }}</div>
      </div>
    </div>
    <div
      v-if="mode === 'calendar'"
      class="border border-neutral-600 grid grid-cols-7"
    >
      <div
        v-for="daySymbol in daySymbolArr"
        :key="daySymbol"
        class="border border-neutral-600 text-center"
      >
        {{ daySymbol }}
      </div>
      <div
        v-for="day in days"
        :key="day"
        class="border border-neutral-600 h-20"
      >
        <div class="text-center">{{ day }}</div>
        <div></div>
      </div>
    </div>
    <div class="mx-6 my-10 flex flex-col gap-2">
      <button
        v-if="mode === 'logs'"
        class="bg-neutral-800 text-neutral-200 w-full py-2"
      >
        add
      </button>
      <button
        v-if="mode === 'logs'"
        class="bg-neutral-100 border-2 border-neutral-800 w-full py-1.5 box-border"
      >
        select month
      </button>
      <button
        class="bg-neutral-100 border-2 border-neutral-800 w-full py-1.5"
        @click="updateMode"
      >
        {{ mode === "logs" ? "calendar" : "logs" }}
      </button>
    </div>
  </section>
</template>
