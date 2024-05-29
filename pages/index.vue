<script setup>
const loading = ref(false);
</script>

<template>
  <div class="grid gap-4 w-full">
    <header class="item-start flex justify-between">
      <div class="grow">
        <p>Hi, welcome back Dan !</p>
        <h1>Dashboard</h1>
      </div>
      <div class="bg-neutral-200 w-[120px] h-[36px]"></div>
    </header>

    <main class="grid gap-4">
      <div class="flex items-center gap-4">
        <div  v-for="(item, index) in 3" :key="index" class="w-[120px] h-[36px] bg-neutral-200"></div>
      </div>
      <section>
        <div class="w-full h-[360px] bg-neutral-200"></div>
      </section>
    </main>
    <footer>
      <div class="flex items-center gap-4">
        <div v-for="(item, index) in 3" :key="index" class="w-full h-[260px] bg-neutral-200"></div>
      </div>
    </footer>
  </div>
</template>
