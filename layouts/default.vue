<script setup lang="ts">
import "@unocss/reset/tailwind.css";
import { useMagicKeys } from "@vueuse/core";

const keys = useMagicKeys();
const reference = ref(false);

watch(keys.space, (v) => (reference.value = !reference.value));
</script>

<template>
  <video
    class="min-w-screen left-0 absolute top-0 pointer-events-none"
    autoplay
    muted
    loop
  >
    <source src="/EP9A2_904_Homescreen.mp4" type="video/mp4" />
    Your browser does not support the video tag.
  </video>

  <img
    v-if="reference"
    src="https://images.squarespace-cdn.com/content/v1/64ee4d43126c653b251eab96/1699173649953-7ZDRIGFLWDOC0YNBD4O7/Main-Menu2.jpg"
    alt="a"
    class="absolute z-100 min-w-dvw pointer-events-none"
  />

  <div class="w-dvw h-dvh max-w-dvw max-h-dvh overflow-hidden">
    <div class="absolute top-2">
      <div>
        <div>
          <svg-logo class="w-24 h-24" />
        </div>

        <div>
          <span>EVOLUTION</span>

          <div>EPISODE 7 // ACT II</div>
        </div>
      </div>
    </div>

    <slot />

    <chat />
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Anton&display=swap");

.font-anton {
  font-family: "Anton", sans-serif;
  font-weight: 400;
  font-style: normal;
}

body {
  overflow: hidden;
  color: white;
}
</style>
