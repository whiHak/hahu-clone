<script setup lang="ts">
import { ref } from 'vue';

const companies = ref([
        { name: 'Natural Science', icon: '/images/job-banner.png'},
        { name: 'Business', icon: '/images/job-banner-2.png'},
        { name: 'Creative Arts', icon: '/images/job-banner-3.jpg'},
        { name: 'Natural Science', icon: '/images/job-banner.png'},
        { name: 'Business', icon: '/images/job-banner-2.png'},
        { name: 'Creative Arts', icon: '/images/job-banner-3.jpg'},
        { name: 'Natural Science', icon: '/images/job-banner.png'},
        { name: 'Business', icon: '/images/job-banner-2.png'},
        { name: 'Creative Arts', icon: '/images/job-banner-3.jpg'},
        { name: 'Natural Science', icon: '/images/job-banner.png'},
        { name: 'Business', icon: '/images/job-banner-2.png'},
        { name: 'Creative Arts', icon: '/images/job-banner-3.jpg'},
])

</script>

<template>
    <div class="bg-[#F3F9F8] dark:bg-[#1B2637] my-10">
    <!-- Featured Jobs Section -->
    <section class="sm:container mx-auto flex flex-col items-center px-4 py-8 overflow-x-hidden">
      <h1
        class="text-3xl md:text-4xl font-bold text-gray-700 pt-10 dark:text-white mb-2 text-center"
      >
        HaHuJobs top posting companies
      </h1>
      <p
        class="text-sm font-medium text-gray-600 mb-8 text-center dark:text-[#C7CACF]"
      >
      Below are some of the companies with a high number of vacancy announcements since the start of our aggregation services in 2019
      </p>
      <div class="relative rounded-2xl overflow-hidden py-10">
        <div
          class="absolute inset-y-0 left-0 w-270 bg-gradient-to-r from-[#F3F9F8] dark:from-[#1B2637] to-transparent z-100 pointer-events-none"
        ></div>
        <div
          class="absolute inset-y-0 right-0 w-270 bg-gradient-to-l from-[#F3F9F8] dark:from-[#1B2637] to-transparent z-100 pointer-events-none"
        ></div>
        <UCarousel
          v-slot="{ item: company }"
          loop
          auto-scroll
          :items="companies"
          :autoplay="{ 
            delay: 7000,
          }"
          :ui="{
            dot: 'w-2 h-1 gap-0 bg-[#777]',
            dots: 'mb-5',
            item: 'basis-1/10',
          }"
          class="w-full  gap-0 relative z-0 "
        >
        <div class="bg-white w-38 h-38 rounded-xl shadow-md p-4 flex flex-col items-center justify-center text-center hover:shadow-lg transition cursor-pointer">
          <img :src="company.icon" :alt="company.name" class="w-full mb-4" />
        </div>
        </UCarousel>
      </div>
    </section>
  </div>
</template>