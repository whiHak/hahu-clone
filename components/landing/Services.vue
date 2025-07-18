<script setup lang="ts">
import { ref } from 'vue';

const services = ref([
  { name: 'Natural Science', icon: '/images/build_career_profile.png', description: "HaHuJobs offers digital career profiling, job application and subscription based relevant vacancy announcement notifications to job seekers that sign up on its primary service deployment." },
    { name: 'Business', icon: '/images/job_application.png', description: "HaHuJobs offers digital career profiling, job application and subscription based relevant vacancy announcement notifications to job seekers that sign up on its primary service deployment." },
    { name: 'Creative Arts', icon: '/images/vacancy_notification.png', description: "HaHuJobs offers digital career profiling, job application and subscription based relevant vacancy announcement notifications to job seekers that sign up on its primary service deployment." },
])
</script>

<template>
  <div class="sm:container mx-auto px-4 py-8">
    <section class="flex flex-col items-center">
      <h1 class="text-3xl md:text-4xl font-bold text-gray-700 dark:text-white mb-2 text-center">
        Services
      </h1>
      <p
        class="text-sm font-medium text-gray-600 dark:text-[#C7CACF] mt-5 mb-8 text-wrap max-w-3xl text-center"
      >
        HaHuJobs offers digital career profiling, job application and
        subscription based relevant vacancy announcement notifications to job
        seekers that sign up on its primary service deployment.
      </p>
      <div class="overflow-x-hidden h-[400px]">
        <UCarousel
          v-slot="{ item: service }"
          dots
          :items="services"
          :ui="{ 
            container: 'gap-[20px] w-full align',
            dots: 'flex gap-2 self-center justify-center',
            dot: 'bg-[#009688] w-3 h-1 rounded-[0px] focus:bg-[#009688] gap-2 self-center justify-center',
            item: 'md:basis-1/3 ml-2 sm:-ml-2'
          }"
          class="max-w-screen gap-[20px] mx-auto relative z-0"
        >
        <div class="bg-white dark:bg-[#1B2637] rounded-xl mx-auto border-2 border-gray-100 dark:border-[#1B2637] hover:border-[#009688] shadow-md p-4 flex flex-col items-center justify-center text-center hover:shadow-lg transition cursor-pointer">
          <img :src="service.icon" :alt="service.name" class="w-40 h-40 mb-4" />
          <h2 class="text-lg font-bold text-[#009688] dark:text-white mb-2">{{ service.name }}</h2>
          <p class="text-gray-600 dark:text-[#C7CACF] text-sm text-wrap w-60">{{ service.description }}</p>
        </div>
    
        </UCarousel>
      </div>
    </section>
  </div>
</template>
