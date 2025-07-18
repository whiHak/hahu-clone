<script setup lang="ts">

    const sectors = ref([
        { name: 'Natural Science', icon: '/images/business.png', positions: 31 },
        { name: 'Business', icon: '/images/health-care.svg', positions: 279 },
        { name: 'Legal Services', icon: '/images/engineering.svg', positions: 13 },
        { name: 'Creative Arts', icon: '/images/legal-service.svg', positions: 23 },
        { name: 'Education', icon: '/images/engineering.svg', positions: 63 },
        { name: 'Hospitality', icon: '/images/creative-art.svg', positions: 22 },
        { name: 'Low and Medium Skilled Worker', icon: '/images/natural-science.svg', positions: 71 },
        { name: 'Engineering', icon: '/images/transport-and-logistics.svg', positions: 160 },
        { name: 'Transportation & Logistics', icon: '/images/engineering.svg', positions: 47 },
        { name: 'Finance', icon: '/images/engineering.svg', positions: 182 },
        { name: 'ICT', icon: '/images/finance.svg', positions: 41 },
        { name: 'Health Care', icon: '/images/business.png', positions: 72 },
        { name: 'ICT', icon: '/images/health-care.svg', positions: 41 },
        { name: 'Health Care', icon: '/images/natural-science.svg', positions: 72 },
      ])
</script>

<template>
  <div class="sm:container mx-auto px-4 py-8">
    <section class="flex flex-col items-center">
      <h1 class="text-3xl md:text-4xl font-bold text-gray-700 dark:text-white mb-2 text-center">
        Career sectors
      </h1>
      <p class="text-sm font-medium text-gray-600 mb-8 mt-5 dark:text-[#C7CACF] text-center">
        Based on the local labor market trend in Ethiopia we categorize our vacancies into fourteen sectors
      </p>
      <div class="grid justify-center w-full grid-cols-2 gap-4 md:flex md:items-center md:flex-wrap 2xl:gap-7 p-5 mt-4">
        <div v-for="(sector, idx) in sectors" :key="idx" class="w-full overflow-hidden sm:w-32 sm:h-32 transition-shadow duration-700 ease-in-out bg-white rounded-lg shadow-xl cursor-pointer md:rounded-xl md:w-50 md:h-50 hover:drop-shadow-2xl dark:bg-[#1B2637] p-3 flex flex-col items-center justify-center text-center hover:shadow-lg">
          <img :src="sector.icon" :alt="sector.name" class="object-contain w-10 h-10 sm:w-8 sm:h-8 md:w-22 md:h-22 " />
          <p class="md:text-md xs:text-sm font-bold text-[#009688] py-2 line-clamp-1 sm:line-clamp-2">{{ sector.name }}</p>
          <p class="text-gray-600 dark:text-white  [@media(min-width:24rem)]:text-sm sm:text-md">{{ sector.positions }} Open positions</p>
        </div>
      </div>
    </section>
  </div>
</template>


