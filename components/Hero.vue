<script>

</script>
<template>
    <div class="container mx-auto px-4 py-8">
    <!-- Hero Section -->
    <section class="flex flex-col items-center">
      <h1 class="text-3xl md:text-4xl font-bold text-gray-700 mb-2 text-center">
        All Ethiopian Jobs in One Place.
      </h1>
      <p class="text-sm font-medium text-gray-600 mb-8 text-center">
        Find career opportunities in Ethiopia
      </p>
      <div class="flex w-full max-w-xl mb-10 responsive-layout">
        <input
          type="text"
          placeholder="Job title, city or keyword..."
          class="flex-1 px-4 py-2 rounded-b-md border border-gray-300 focus:outline-gray-300 hover:ring-[1px] hover:ring-[#009688] text-lg"
        />
        <button
          class="flex items-center gap-2 px-6 py-3 bg-[#009688] text-white font-bold rounded-r-md transition cursor-pointer"
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
          <span class="text-base text-gray-700 font-medium">{{
            stat.label
          }}</span>
        </div>
      </div>
    </section>
  </div>
  <img src="/banner.svg" alt="Logo" />
</template>