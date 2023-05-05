<template>
  <div class="flex ml-20 mb-6">
    <p class="text-md text-orange-800 font-bold">
      Total number of living characters : {{ aliveCount }}
    </p>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

const props = defineProps({
  aliveCount: { type: Number, required: true },
});
</script>