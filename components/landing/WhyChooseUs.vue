<script setup lang="ts">
// No script logic needed for static UI
</script>

<template>
  <section class=" container mx-auto dark:bg-[#02201D] flex flex-col-reverse lg:flex-row justify-between items-start pt-12 pb-0 px-0">
    <div class="max-w-xl ml-10 flex-1">
      <h2 class="text-3xl md:text-4xl font-extrabold text-gray-800 dark:text-white  mb-6 leading-tight">
        <span>What makes us</span><br />
        <span>standout from the rest</span>
      </h2>
      <p class="text-gray-700 dark:text-[#C7CACF] md:text-md mb-4 leading-relaxed">
        HaHuJobs Primary services are deployments targeting the needs of the Ethiopian jobseeker, with both online and assisted models the platform is tool intended to assist the process of looking for a job at all levels of employment. It features vacancy aggregation and posting from various sources as well as enterprises, builds career profiles, apply for jobs, and subscribe to customized alerts for each user via a channel of their choice. HaHuJobs primary also offers standardized classification of all vacancies both sourced from HaHuJobs enterprise services and other manual and digital vacancy platforms.
      </p>
      <p class="text-gray-700 dark:text-[#C7CACF] text-base md:text-md mb-4 leading-relaxed">
        Our vacancy classification follows a combination of ILOs ISCO 8 and the O*Net occupation classification with modifications to the Ethiopian labor market trend. Each vacancy will be given a four-digit occupation taxonomy identification code to determine it's overall standard requirements in terms of skill, knowledge, ability, and expected activities.
      </p>
      <div class="my-6">
        <button class="bg-teal-600 hover:bg-teal-700 text-white rounded-md px-7 py-1 font-semibold flex items-center gap-2 transition">
          Explore more
          <span class="text-xl">→</span>
        </button>
      </div>
      <div class="flex gap-8 mt-4">
        <img src="/images/telegram.svg" alt="Telegram" class="w-5 h-5 hover:scale-110 transition" />
        <img src="/images/facebook-circular.svg" alt="Facebook" class="w-5 h-5 hover:scale-110 transition" />
        <img src="/x.svg" alt="X" class="w-5 h-5 hover:scale-110 transition" />
        <img src="/images/linkedin_color.svg" alt="LinkedIn" class="w-5 h-5 hover:scale-110 transition" />
      </div>
    </div>
    <div class=" min-w-[220px] max-w-xl mx-auto mb-12 lg:mt-0 mr-10">
      <img src="/images/hahu_robot.svg" alt="Robot" class="relative top-10 lg:-translate-y-1 hover:scale-110 transition duration-300 w-[380px] z-20" />
    </div>
  </section>
</template>