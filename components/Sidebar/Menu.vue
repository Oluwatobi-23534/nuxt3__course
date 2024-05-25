<script setup>
import { ref } from 'vue';

const items = ref([
  {
    title: "Overview",
    path: "/overview",
    icon: "mage:dashboard-4-fill"
  },
  {
    title: "Transactions",
    path: "/transactions",
    icon: "grommet-icons:transaction"
  },
  {
    title: "Account",
    path: "/account",
    icon: "mdi:account-cog-outline"
  },
  {
    title: "Contacts",
    path: "/contacts",
    icon: "hugeicons:contact-01"
  },
  {
    title: "Settings",
    path: "/settings",
    icon: "ic:baseline-settings"
  },
]);
</script>


<template>
  <div>
    <header
      class="flex items-center gap-2 p-4 hover:scale-[101%] transition cursor-pointer"
    >
      <Logo />
      <p class="font-bold">Nuxt Finance</p>
    </header>
    <div class="px-4 grow">
      <div class="grid gap-2">
        <div v-for="(item, index) in items" :key="index" class="flex items-center gap-2 px-2 py-1 transition hover:bg-zinc-100 cursor-pointer">
          <Icon size="20" :name="item.icon" color="black" />
          <span>{{ item.title }}</span>
        </div>
      </div>
    </div>
  </div>
</template>
