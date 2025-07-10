<script>
const  services= [
    { name: 'Natural Science', icon: '/images/engineering.svg', positions: 31 },
    { name: 'Business', icon: '/images/engineering.svg', positions: 279 },
    { name: 'Creative Arts', icon: '/images/engineering.svg', positions: 23 },
]
</script>

<template>
  <div class="container mx-auto px-4 py-8">
    <section class="flex flex-col items-center">
      <h1 class="text-3xl md:text-4xl font-bold text-gray-700 dark:text-white mb-2 text-center">
        Services
      </h1>
      <p
        class="text-sm font-medium text-gray-600 dark:text-[#C7CACF] mb-8 text-wrap max-w-3xl text-center"
      >
        HaHuJobs offers digital career profiling, job application and
        subscription based relevant vacancy announcement notifications to job
        seekers that sign up on its primary service deployment.
      </p>
      <div class="grid grid-cols-2 sm:grid-cols-4 md:grid-cols-5 jusic lg:grid-cols-6 gap-6 w-full  mt-4">
        <UCarousel
          v-slot="{ service }"
          dots
          :items="services"
          :ui="{ 
            container: 'gap-[20px] align-items-center',
            dot: 'w-2 h-1 gap-0 bg-[#777] ',
            dots: 'ml-22 mt-5',

          }"
          class="w-full max-w-xs "
        >
        <div class="bg-white rounded-xl shadow-md p-4 flex flex-col items-center justify-center text-center hover:shadow-lg transition">
          <img :src="service.icon" :alt="service.name" class="w-16 h-16 mb-4" />
          <h2 class="text-lg font-bold text-[#009688] mb-2">{{ service.name }}</h2>
          <p class="text-gray-600 text-base">{{ service.positions }} Open positions</p>
        </div>
    
        </UCarousel>
      </div>
    </section>
  </div>
</template>
