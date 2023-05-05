<template>
  <a class="w-full md:w-6/12 lg:w-3/12 lg:mb-0 mb-12 px-4 hover:drop-shadow-2xl cursor-pointer">
    <div class="px-6">
      <img
        :alt="title"
        :src="image"
        class="rounded-xl shadow-lg max-w-full h-auto align-middle border-none m-auto relative"
      >
      <span class="relative bottom-72 left-64 bg-blue-600 text-white rounded-md px-2 py-1 text-sm font-light">{{ status }}</span>
      <div class="pt-1 text-center">
        <h1 class="text-gray-900 text-xl font-bold leading-normal">{{ title }}</h1>
        <p class="text-blue-gray-700 text-base font-light leading-relaxed -mt-2 pb-8">{{ subtitle }}</p>
      </div>
    </div>
  </a>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

const props = defineProps({
  title: { type: String, required: true },
  subtitle: { type: String, required: true },
  image: { type: String, required: true },
  status: { type: String, required: true },
});
</script>
