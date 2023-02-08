<script setup lang="ts">
const months = [
  "January",
  "February",
  "March",
  "April",
  "May",
  "June",
  "July",
  "August",
  "September",
  "October",
  "November",
  "December",
];
onMounted(() => {});
</script>

<template>
  <div>
    <div class="absolute inset-x-0 bottom-0 sm:relative">
      <div class="flex justify-center gap-3 max-w-sm mx-auto sm:hidden">
        <label for="month-filter">month</label>
        <select id="month-filter" name="month-filter">
          <option
            v-for="month in months"
            :key="month"
            :value="month.toLowerCase().substring(0, 3)"
          >
            {{ month.toLowerCase() }}
          </option>
        </select>

        <label for="year-filter">year</label>
        <select id="year-filter" name="year-filter">
          <option value="2020">2020</option>
          <option value="2021">2021</option>
          <option value="2022">2022</option>
        </select>
      </div>
      <header class="flex justify-between px-6 py-4 sm:relative">
        <nav>
          <ul class="flex gap-3">
            <li>future</li>
            <li>monthly</li>
            <li>daily</li>
          </ul>
        </nav>
        <button>logout</button>
      </header>
    </div>
    <slot />
  </div>
</template>
