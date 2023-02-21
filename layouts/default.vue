<template>
  <div>
    <div class="absolute inset-x-0 bottom-0 sm:relative">
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
