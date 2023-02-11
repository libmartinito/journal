<script setup lang="ts">
definePageMeta({
  layout: false,
});
const client = useSupabaseAuthClient();
const signIn = async () => {
  const { error } = await client.auth.signInWithPassword({
    email: email.value,
    password: password.value,
  });
  if (error) {
    console.error(error);
  }
};
const email = ref<string>("");
const password = ref<string>("");
</script>

<template>
  <div class="flex flex-col justify-center h-full">
    <div class="text-neutral-600 text-4xl text-center">journal</div>
    <div class="flex flex-col mx-8 my-14">
      <button
        class="border-2 border-neutral-800 flex justify-center items-center gap-4 px-4 py-2"
      >
        <i class="devicon-github-original text-2xl text-neutral-800"></i>
        <div>sign in with github</div>
      </button>
      <div class="flex justify-center items-center gap-6 my-6">
        <div class="h-0.5 w-full bg-neutral-600"></div>
        <div>or</div>
        <div class="h-0.5 w-full bg-neutral-600"></div>
      </div>
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
        type="passsword"
        placeholder="password"
        required
      />
      <button
        class="bg-neutral-800 text-neutral-200 font-bold mt-8 mb-4 px-4 py-2"
        @click="signIn"
      >
        sign in
      </button>
      <div class="text-xs">
        don't have an account?
        <span class="whitespace-nowrap"
          >sign up <span class="underline">here</span>.</span
        >
      </div>
    </div>
  </div>
</template>
