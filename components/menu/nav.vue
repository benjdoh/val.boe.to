<script setup lang="ts">
const mainLink = "play";
const links = [
  mainLink,
  "premier",
  "career",
  "battlepass",
  "collection",
  "agents",
  "store",
];
const focused = ref<string[]>([]);
</script>

<template>
  <div
    class="absolute left-13 top-1/2 transform -translate-y-1/2 flex flex-col gap-7.5"
  >
    <span
      v-for="link of links"
      class="flex gap-5 items-center font-anton font-bold text-5xl uppercase pointer-events-auto tracking-wide"
      @mouseover="focused.push(link)"
      @mouseleave="focused = focused.filter((v) => v !== link)"
    >
      <div class="w-2 h-2">
        <span
          :class="[
            'block w-2 h-2 bg-white transform transition',
            focused.includes(link) ? 'rotate-135' : 'rotate-45 ',
          ]"
        />
      </div>

      <nuxt-link
        :to="`/${link}`"
        :class="[
          'transition-all',
          link === mainLink ? 'text-red-500 text-8xl' : '',
          focused.includes(link) ? 'text-cyan-300! pl-5' : '',
        ]"
      >
        {{ link }}
      </nuxt-link>
    </span>
  </div>
</template>
