<script setup lang="ts">
import { stats } from '~/constants';

</script>
<template>
    <div class="sm:container mx-auto px-4 py-8">
    <!-- Hero Section -->
    <section class="flex flex-col items-center">
      <h1 class="text-4xl font-bold text-gray-700 dark:text-white mb-2 text-center">
        All Ethiopian Jobs in One Place.
      </h1>
      <p class="text-md font-medium text-gray-600 mb-8 dark:text-[#C7CACF] text-center">
        Find career opportunities in Ethiopia
      </p>
      <div class="flex mx-auto flex-col [@media(min-width:24rem)]:flex-row items-center gap-1 sm:0 w-full max-w-sm sm:max-w-md mb-10 transition-all duration-1000 ease-in-out focus-within:max-w-lg">
        <input
          type="text"
          placeholder="Job title, city or keyword..."
          class="flex-1 px-4 py-[5px] [@media(min-width:24rem)]:py-[9px] w-[75vw] xsm:w-[45vw] sm:w-[40vw] md:w-[40vw] lg:w-[35vw] xl:w-[30vw] 2xl:w-[20vw] 3xl:w-[400px] 3xl:max-w-[600px] rounded-l-lg border-1 border-gray-300 dark:border-[#444F60] dark:focus:border-[#444F60] dark:focus:outline-[#444F60] hover:ring-[1px] hover:ring-[#009688] text-lg dark:placeholder-[#C7CACF] placeholder-[#6B7280] dark:bg-[#444F60] bg-white placeholder:font-bold focus:ring-transparent placeholder:text-[16px]  [@media(min-width:24rem)]:w-[200px]  [@media(min-width:24rem)]:ml-5  focus:rounded-bl-[0]"
        />
        <button
          class="flex items-center gap-2 px-6 py-3 text-nowrap bg-[#009688] text-white w-max font-bold rounded-md rounded-l-[0] transition cursor-pointer"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-5 h-5"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M21 21l-4.35-4.35m0 0A7.5 7.5 0 104.5 4.5a7.5 7.5 0 0012.15 12.15z"
            />
          </svg>
          Find Job
        </button>
      </div>
      <div class="flex justify-center gap-12 mb-8">
        <div
          v-for="stat in stats"
          :key="stat.label"
          class="flex flex-col items-center"
        >
          <span class="text-3xl font-bold text-teal-600">{{ stat.value }}</span>
          <span class="text-base text-gray-700 dark:text-[#C7CACF] font-medium">{{
            stat.label
          }}</span>
        </div>
      </div>
    </section>
    <img src="/banner.svg" alt="Logo" class="w-full mt-5" />
  </div>
  <img src="/images/dots.svg" alt="Logo" class="absolute hidden dark:md:block top-30 left-0 w-60" />
</template>