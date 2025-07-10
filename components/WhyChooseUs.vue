<script setup lang="ts">
// No script logic needed for static UI
</script>

<template>
  <section class=" container mx-auto flex flex-col lg:flex-row justify-between items-start pt-12 pb-0 px-0">
    <div class="max-w-2xl ml-10 flex-1">
      <h2 class="text-4xl md:text-5xl font-extrabold text-gray-800 mb-6 leading-tight">
        <span>What makes us</span><br />
        <span>standout from the rest</span>
      </h2>
      <p class="text-gray-700 text-base md:text-lg mb-4 leading-relaxed">
        HaHuJobs Primary services are deployments targeting the needs of the Ethiopian jobseeker, with both online and assisted models the platform is tool intended to assist the process of looking for a job at all levels of employment. It features vacancy aggregation and posting from various sources as well as enterprises, builds career profiles, apply for jobs, and subscribe to customized alerts for each user via a channel of their choice. HaHuJobs primary also offers standardized classification of all vacancies both sourced from HaHuJobs enterprise services and other manual and digital vacancy platforms.
      </p>
      <p class="text-gray-700 text-base md:text-lg mb-4 leading-relaxed">
        Our vacancy classification follows a combination of ILOs ISCO 8 and the O*Net occupation classification with modifications to the Ethiopian labor market trend. Each vacancy will be given a four-digit occupation taxonomy identification code to determine it's overall standard requirements in terms of skill, knowledge, ability, and expected activities.
      </p>
      <div class="my-6">
        <button class="bg-teal-600 hover:bg-teal-700 text-white rounded-md px-7 py-3 font-semibold flex items-center gap-2 transition">
          Explore more
          <span class="text-xl">→</span>
        </button>
      </div>
      <div class="flex gap-6 mt-4">
        <a href="#" aria-label="Telegram"><img src="/images/telegram.svg" alt="Telegram" class="w-7 h-7 hover:scale-110 transition" /></a>
        <a href="#" aria-label="Facebook"><img src="/images/facebook-circular.svg" alt="Facebook" class="w-7 h-7 hover:scale-110 transition" /></a>
        <a href="#" aria-label="X"><img src="/x.svg" alt="X" class="w-7 h-7 hover:scale-110 transition" /></a>
        <a href="#" aria-label="LinkedIn"><img src="/images/linkedin_color.svg" alt="LinkedIn" class="w-7 h-7 hover:scale-110 transition" /></a>
      </div>
    </div>
    <div class="relative flex-1 flex flex-col items-center min-w-[320px] max-w-lg mx-auto mt-12 lg:mt-0 mr-10">
      <img src="/images/hahu_robot.svg" alt="Robot" class=" left-1/2 -translate-x-1/2 bottom-8 w-[180px] z-20" />
    </div>
  </section>
</template>