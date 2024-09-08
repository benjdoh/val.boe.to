<script setup lang="ts">
const recepient = ref("Party");
</script>

<template>
  <div
    class="absolute bottom-0 left-0 w-md bg-black/50 block h-8 text-sm items-center flex"
  >
    <span class="font-medium text-blue-200/75 tracking-wide px-4">
      {{ recepient }}:
    </span>

    <input type="text" class="flex-grow bg-transparent outline-none" />
  </div>

  <div></div>
</template>
