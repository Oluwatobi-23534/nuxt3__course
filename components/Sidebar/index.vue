<script setup>
const open = ref(true);
</script>

<template>
  <div class="">
    <div class="z-50 items-center justify-between w-full h-full p-4 flex lg:hidden">
      <Logo/>
      <Icon class="z-50 cursor-pointer left-2 top-2" size="30" name="ci:menu-alt-01" @click="open=true"/>
      <div v-if="open" class="fixed top-0 left-0 z-[999] w-full h-full  bg-white">
        <Icon class="absolute z-50 cursor-pointer right-4 top-4" size="30" name="ri:close-line" @click="open=false"/>
        <SidebarMenu/>
      </div>
    </div>
    <div
      class="hidden lg:flex w-[200px] h-screen flex flex-col justify-between border-r"
    >
      <SidebarMenu />
      <div>UserItem</div>
    </div>
  </div>
</template>
