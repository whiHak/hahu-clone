<script setup lang="ts">
// No script logic needed for static UI
</script>

<template>
  <section class="flex flex-col md:flex-row items-start bg-[#f8fdfc] rounded-3xl py-12 px-0 my-10 justify-center">
    <div class="flex-1 flex items-center justify-center min-w-[320px]">
      <img src="/images/job_application.png" alt="Job Application" class="max-w-[380px] w-full" />
    </div>
    <div class="flex-1 max-w-2xl md:ml-16 mt-10 md:mt-0">
      <h2 class="text-3xl md:text-4xl font-extrabold text-gray-800 mb-4">Post vacancy</h2>
      <p class="text-gray-700 text-base md:text-lg mb-6 leading-relaxed">
        HaHuJobs offers dedicated enterprise cloud services for a full human resource management platform with an affordable price package. Posting vacancy is completely free, and only requires to follow the below listed steps.
      </p>
      <div class="mb-8">
        <div class="flex items-start mb-4">
          <div class="text-2xl font-bold text-gray-700 mr-4 min-w-[54px]">01</div>
          <div>
            <div class="font-bold text-base text-gray-800 mb-1">Receive</div>
            <div class="text-gray-700 text-sm leading-snug">You contact us through one of our outlets with the details of your vacancy. You can click the button below to review ways to share your vacancy and review the required information we need to publish your vacancy on all our outlets.</div>
          </div>
        </div>
        <div class="flex items-start mb-4">
          <div class="text-2xl font-bold text-gray-700 mr-4 min-w-[54px]">02</div>
          <div>
            <div class="font-bold text-base text-gray-800 mb-1">Validate</div>
            <div class="text-gray-700 text-sm leading-snug">Our service officers will receive the details from your organization via the channel you communicated it in. They will review the details provided to validate all required information is available and build validate the legitimacy of the vacancy.</div>
          </div>
        </div>
        <div class="flex items-start mb-4">
          <div class="text-2xl font-bold text-gray-700 mr-4 min-w-[54px]">03</div>
          <div>
            <div class="font-bold text-base text-gray-800 mb-1">Publish</div>
            <div class="text-gray-700 text-sm leading-snug">All vacancy details will then go through our standardized categorization process for taxonomy identification and reorganization of information if required so it fits the publishing structure of our outlets, then will be approved for publishing.</div>
          </div>
        </div>
      </div>
      <div class="mt-6 flex flex-col items-start relative">
        <div class="text-base text-gray-700 mb-2">Sign up to HaHu Jobs Enterprise</div>
        <button class="bg-teal-600 hover:bg-teal-700 text-white rounded-md px-8 py-3 font-semibold flex items-center gap-2 transition">
          Post vacancy
          <span class="text-xl">→</span>
        </button>
        <svg class="absolute left-32 -top-8 pointer-events-none" width="60" height="40" viewBox="0 0 60 40" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M10 10 Q30 0 50 20" stroke="#10b0a6" stroke-width="3" fill="none"/><path d="M50 20 L45 15 M50 20 L45 25" stroke="#10b0a6" stroke-width="3" fill="none"/></svg>
      </div>
    </div>
  </section>
</template>