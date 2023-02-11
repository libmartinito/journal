<script setup lang="ts">
definePageMeta({
  layout: false,
});
const client = useSupabaseAuthClient();
const signUp = async () => {
  const { error } = await client.auth.signUp({
    email: email.value,
    password: password.value,
  });
  if (error) {
    console.error(error);
  }
};
const email = ref<string>("");
const password = ref<string>("");
const reEnteredPassword = ref<string>("");
</script>

<template>
  <div class="flex flex-col justify-center h-full">
    <div class="text-neutral-600 text-4xl text-center">journal</div>
    <div class="flex flex-col mx-8 my-14">
      <input
        v-model="email"
        class="mt-4 px-4 py-2"
        type="email"
        placeholder="email"
        required
      />
      <input
        v-model="password"
        class="mt-4 px-4 py-2"
        type="password"
        placeholder="password"
        required
      />
      <input
        v-model="reEnteredPassword"
        class="mt-4 px-4 py-2"
        type="password"
        placeholder="re-enter password"
        required
      />
      <button
        class="bg-neutral-800 text-neutral-200 font-bold mt-8 mb-4 px-4 py-2"
        @click="signUp"
      >
        sign up
      </button>
      <div class="text-xs">
        already have an account?
        <span class="whitespace-nowrap"
          >sign in <span class="underline">here</span>.</span
        >
      </div>
    </div>
  </div>
</template>
