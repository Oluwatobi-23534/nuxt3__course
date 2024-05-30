<template>
  <div
    class="m-2 p-2 gap-2 flex items-center justify-start border rounded cursor-pointer hover:bg-neutral-50 transition"
  >
    <div
      class="w-10 h-10 bg-green-500 rounded-full flex items-center justify-center font-bold text-white"
    >
      {{ name[0] }}
    </div>
    <div>
      <p class="font-bold text-black m-0 leading-1 text-sm">{{ name }}</p>
      <p class="m-0 text-xs">{{ description }}</p>
    </div>
  </div>
</template>

<script setup>
const loading = ref(false);
const name = ref("Dan Jones");
const description = ref("Devloper & Artist");
</script>
