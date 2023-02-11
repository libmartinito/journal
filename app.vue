<script setup lang="ts">
useHead({
  link: [
    {
      rel: "stylesheet",
      type: "text/css",
      href: "https://cdn.jsdelivr.net/gh/devicons/devicon@v2.15.1/devicon.min.css",
    },
  ],
});
</script>
<template>
  <div
    class="bg-neutral-100 text-neutral-800 font-mono max-w-xl mx-auto h-screen"
  >
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>
