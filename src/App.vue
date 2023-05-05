<template>
  <transition
    enter-active-class="transition-opacity duration-500"
    enter-from-class="opacity-0"
    enter-to-class="opacity-100"
    leave-active-class="transition-opacity duration-500"
    leave-from-class="opacity-100"
    leave-to-class="opacity-0"
    mode="out-in">
    <div
      v-if="showSplashScreen"
      class="bg-red-300 h-screen flex items-center justify-center text-4xl uppercase text-white font-bold">
      SPLASH SCREEN
    </div>
    <div
      v-else
      class="bg-blue-300 h-screen flex items-center justify-center text-4xl uppercase text-white font-bold">
      REPORT SCREEN
    </div>
  </transition>
</template>

<script lang="ts" setup>
import { ref, unref } from 'vue'
const showSplashScreen = ref(true)
setTimeout(() => {
  showSplashScreen.value = !unref(showSplashScreen)
}, 1000)
</script>
