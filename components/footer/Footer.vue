<script setup lang="ts">
</script>

<template>
    <footer class="w-full mt-16  font-sans">
      <div class="sm:container mx-auto flex flex-wrap justify-between items-start px-16 py-2 gap-10">
        <div class="flex flex-col min-w-[60px] max-w-[320px]">
          <div class="font-bold text-base mb-2 text-gray-800 dark:text-white underline">Get Started</div>
          <a href="#" class="text-gray-700 text-sm mb-1 hover:text-teal-500 dark:text-white transition font-medium">Sign up</a>
          <a href="#" class="text-gray-700 text-sm mb-1 hover:text-teal-500 dark:text-white transition font-medium">Login</a>
        </div>
        <div class="flex flex-col min-w-[60px] max-w-[320px]">
          <div class="font-bold text-base mb-2 text-gray-800 dark:text-white underline">Quick links</div>
          <a href="#" class="text-gray-700 text-sm mb-1 hover:text-teal-500 dark:text-white transition font-medium">HahuJobs IO</a>
          <a href="#" class="text-gray-700 text-sm mb-1 hover:text-teal-500 dark:text-white transition font-medium">Minab Tech</a>
        </div>
        <div class="flex flex-col items-center min-w-[120px] md:min-w-[320px] max-w-[420px] sm:items-start">
          <img src="/images/minab-logo.png" alt="Minab Logo" class="w-40 mb-2" />
          <p class="text-gray-700 dark:text-white text-sm mt-1 font-medium text-wrap w-72 md:w-120 leading-relaxed">
            HaHuJobs is a cloud based product owned and manged by a technology consulting firm called Minab IT solutions PLC. Minab was founded in 2014 and has an extensive experience in software development for the past nine years.
          </p>
        </div>
        <div class="flex flex-col min-w-[220px] items-center md:items-end">
          <div class="text-base text-gray-700 dark:text-white  mb-1">Powered by</div>
          <img src="/logo_dark_2.svg" alt="HaHuJobs Logo" class="w-[140px] mb-1" />
          <div class="flex gap-2">
            <p class="text-teal-500 text-lg font-semibold">ለሀገር ልጅ </p>
            <p class="text-lg font-semibold dark:text-white">በሀገር!</p>
          </div>
        </div>
      </div>
      <div class="sm:container mx-auto flex flex-col-reverse md:flex-row flex-wrap justify-between items-center border-t pt-10 border-gray-400 px-16 py-4 mt-2">
        <div class="flex items-center gap-6">
          <a href="#" class="text-gray-400 text-sm mr-3 dark:text-white">Privacy policy</a>
          <span class="text-gray-400 dark:text-white text-sm">© 2020 - 2025 HaHuJobs. All rights reserved.</span>
        </div>
        <div class="flex gap-7 mt-2 md:mt-0">
          <img src="/images/telegram.svg" alt="Telegram" class="w-5 h-5 hover:scale-110 transition" />
          <img src="/images/facebook-circular.svg" alt="Facebook" class="w-5 h-5 hover:scale-110 transition" />
          <img src="/x.svg" alt="X" class="w-5 h-5 hover:scale-110 transition" />
          <img src="/images/linkedin_color.svg" alt="LinkedIn" class="w-5 h-5 hover:scale-110 transition" />
        </div>
      </div>
    </footer>
</template>