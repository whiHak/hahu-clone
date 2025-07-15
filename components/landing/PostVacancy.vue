<script setup lang="ts">
// No script logic needed for static UI
</script>

<template >
  <section id="post-vacancy" class="bg-[#f8fdfc] dark:bg-[#1B2637] px-5 sm:py-14 sm:my-14">
    <div class="sm:container mx-auto flex flex-col md:flex-row items-start justify-center">
    <div class="relative top-10 lg:-translate-y-1 flex-1 flex items-center justify-center sm:min-w-[320px]  min-w-30">
      <img src="/images/job_application.png" alt="Job Application" class="max-w-[380px] self-center w-full" />
    </div>
    <div class="flex-1 gap-10 max-w-2xl md:ml-16 mt-10 md:mt-0">
      <h2 class="text-3xl md:text-4xl font-extrabold text-gray-700 text-center sm:text-left dark:text-white mb-4">Post vacancy</h2>
      <p class="text-gray-700 dark:text-[#C7CACF] text-base md:text-sm mb-10 text-center sm:text-left">
        HaHuJobs offers dedicated enterprise cloud services for a full human resource management platform with an affordable price package. Posting vacancy is completely free, and only requires to follow the below listed steps.
      </p>
      <div class=" grid sm:grid-cols-2 gap-3  mb-8">
        <div class="flex flex-col items-start mb-4">
          <div class="flex flex-row items-end">
            <div class="text-5xl font-bold text-gray-600 dark:text-[#009688] min-w-[54px]">01</div>
            <div class=" text-lg ml-3 text-gray-500 dark:text-[#009688] mb-1">Receive</div>
          </div>
          <p class="text-gray-500 dark:text-[#C7CACF] mt-3  text-xs leading-snug">You contact us through one of our outlets with the details of your vacancy. You can click the button below to review ways to share your vacancy and review the required information we need to publish your vacancy on all our outlets.</p>
        </div>
        <div class="flex flex-col items-start mb-4">
          <div class="flex flex-row items-end">
            <div class="text-5xl font-bold text-gray-600 dark:text-[#009688] min-w-[54px]">02</div>
            <div class=" text-lg ml-3 text-gray-500 dark:text-[#009688] mb-1">Receive</div>
          </div>
          <p class="text-gray-500 dark:text-[#C7CACF] mt-3 text-xs leading-snug">You contact us through one of our outlets with the details of your vacancy. You can click the button below to review ways to share your vacancy and review the required information we need to publish your vacancy on all our outlets.</p>
        </div>
        <div class="flex flex-col items-start mb-4">
          <div class="flex flex-row items-end">
            <div class="text-5xl font-bold text-gray-600 dark:text-[#009688] min-w-[54px]">03</div>
            <div class=" text-lg ml-3 text-gray-500 dark:text-[#009688] mb-1">Receive</div>
          </div>
          <p class="text-gray-500 dark:text-[#C7CACF] mt-3 text-xs leading-snug">You contact us through one of our outlets with the details of your vacancy. You can click the button below to review ways to share your vacancy and review the required information we need to publish your vacancy on all our outlets.</p>
        </div>
        <div class="flex flex-col mt-6 items-center gap-3 relative">
          <div class=" text-base text-gray-500 dark:text-[#C7CACF] mb-2">Sign up to HaHu Jobs Enterprise</div>
            <img src="/images/downward-arrow.svg"/>
            <button class="bg-teal-600  hover:bg-teal-700 text-white text-sm rounded-md px-6 py-2 font-semibold flex items-center gap-2 transition cursor-pointer">
              Post vacancy
              <span class="text-xl">→</span>
            </button>
          </div>
        </div>
    </div>
    </div>
  </section>
</template>