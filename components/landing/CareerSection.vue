<script setup lang="ts">

    const sectors = ref([
        { name: 'Natural Science', icon: '/images/engineering.svg', positions: 31 },
        { name: 'Business', icon: '/images/engineering.svg', positions: 279 },
        { name: 'Creative Arts', icon: '/images/engineering.svg', positions: 23 },
        { name: 'Education', icon: '/images/engineering.svg', positions: 63 },
        { name: 'Hospitality', icon: '/images/engineering.svg', positions: 22 },
        { name: 'Low and Medium Skilled Worker', icon: '/images/engineering.svg', positions: 71 },
        { name: 'Transportation & Logistics', icon: '/images/engineering.svg', positions: 47 },
        { name: 'Engineering', icon: '/images/engineering.svg', positions: 160 },
        { name: 'Finance', icon: '/images/engineering.svg', positions: 182 },
        { name: 'Legal Services', icon: '/images/engineering.svg', positions: 13 },
        { name: 'ICT', icon: '/images/engineering.svg', positions: 41 },
        { name: 'Health Care', icon: '/images/engineering.svg', positions: 72 },
      ])
</script>

<template>
  <div class="container mx-auto px-4 py-8">
    <section class="flex flex-col items-center">
      <h1 class="text-3xl md:text-4xl font-bold text-gray-700 dark:text-white mb-2 text-center">
        Career sectors
      </h1>
      <p class="text-sm font-medium text-gray-600 mb-8 mt-5 dark:text-[#C7CACF] text-center">
        Based on the local labor market trend in Ethiopia we categorize our vacancies into fourteen sectors
      </p>
      <div class="grid justify-center w-full grid-cols-2 gap-4 md:flex md:items-center md:flex-wrap 2xl:gap-7 mt-4">
        <div v-for="(sector, idx) in sectors" :key="idx" class="w-24 h-24 overflow-hidden xs:w-32 xs:h-32 xs:p- transition-shadow duration-700 ease-in-out bg-white rounded-lg shadow-xl cursor-pointer md:rounded-xl md:w-60 md:h-60 hover:drop-shadow-2xl dark:bg-[#1B2637] p-4 flex flex-col items-center justify-center text-center hover:shadow-lg">
          <img :src="sector.icon" :alt="sector.name" class="object-contain w-5 h-5 xs:w-8 xs:h-8 md:w-24 md:h-24" />
          <h2 class="md:text-md xs:text-sm font-bold text-[#009688] mb-2">{{ sector.name }}</h2>
          <p class="text-gray-600 dark:text-white text-base">{{ sector.positions }} Open positions</p>
        </div>
      </div>
    </section>
  </div>
</template>


