<script setup lang="ts">
import { stats } from '~/constants';

</script>

<template>
  <div class="container mx-auto px-4 py-8">
    <section class="flex flex-col items-center">
      <h1 class="text-4xl md:text-5xl font-bold text-gray-700 dark:text-white mb-2 text-center">
        Our Latest Statistics
      </h1>

      <div class="flex justify-center md:gap-52 gap-12  mb-8">
        <div
          v-for="stat in stats"
          :key="stat.label"
          class="flex flex-col items-center"
        >
          <span class="text-4xl font-bold text-teal-600">{{ stat.value }}</span>
          <span class="text-base text-gray-700 dark:text-[#C7CACF] font-medium">{{
            stat.label
          }}</span>
        </div>
      </div>
    </section>
  </div>
</template>
