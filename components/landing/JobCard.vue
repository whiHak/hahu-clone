<script setup lang="ts">
import { Menu, vTooltip  } from 'floating-vue';

  defineProps({
    title: { type: String, default: 'Senior Auto Electrician' },
    company: { type: String, default: 'Ethiopian Engineering...' },
    companyLogo: { type: String, default: '/images/job-banner.png' },
    sector: { type: String, default: 'Low and Medium Skilled Worker' },
    category: { type: String, default: 'Auto Mechanical Skilled Worker' },
    location: { type: String, default: 'Addis Ababa' },
    experience: { type: String, default: '6 years' },
    positions: { type: String, default: '2 Positions' },
    type: { type: String, default: 'Full Time' },
    summary: { type: String, default: 'TVET Level IV in Auto Electrician or in a related field of study with relevant work experience, out of which 2 years in a similar role Duties and Responsibilitie...' },
    daysLeft: { type: String, default: '3 Days Left' },
    views: { type: String, default: '10k' },
    sectorIcon: { type: String, default: '/images/business.png' },
    locationIcon: { type: String, default: '/images/engineering.svg' },
  })
</script>

<template>
  <div class="relative bg-white dark:bg-[#1B2637] rounded-xl hover:shadow-lg  border-2 border-gray-200 dark:border-[#02201D] hover:border-[#009688] p-5 w-full min-w-[300px] h-[500px] flex flex-col gap-3 cursor-pointer">
    <!-- Featured Badge -->
     <div class=" flex gap-2 items-center w-8 h-8 ">
       <img src="/images/bookmark.png" alt="Featured" class="w-4 h-4 absolute flex items-center justify-center px-4 text-xs text-center top-2 sm:top-0 right-10 sm:right-32 gap-x-2 md:text-base border-primary" />
       <div class="bg-[#009688] absolute top-[-2px] right-[-1px] flex items-center justify-center w-12 h-8 px-3 py-1 sm:py-0 sm:px-4 sm:w-36 rounded-tr-xl gap-x-1 sm:gap-x-2 rounded-bl-md">
         <img src="/images/hahu_featured.svg" alt="Featured"/>
         <p class="hidden text-white sm:block font-light text-sm">Featured</p>
       </div>
     </div>
    <!-- Days Left -->
    <div class="absolute top-3 left-3 flex items-center gap-1 text-xs text-teal-600 font-medium">
      <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
      {{ daysLeft }}
    </div>
    <div class="flex items-center gap-2">
      <!-- Company Logo and Name -->
      <div class="flex flex-1 flex-col items-center gap-3 mt-4">

        <Menu placement="right" >
          <button>
            <img :src="companyLogo" alt="EEC Logo" class=" rounded p-1 md:h-[60px] object-contain w-20 md:w-32 mb-3 " />
          </button>
          <template #popper>
            <div class="flex gap-2 w-60 bg-white rounded-lg shadow-lg p-4">
              <img :src="companyLogo" alt="EEC Logo" class=" rounded p-1 w-10 h-10" />
              <div class="flex flex-col gap-2">
                <span class="text-gray-700 dark:text-[#C7CACF] font-semibold text-base leading-tight">{{ company }}</span>
                <p class="text-sm text-gray-500">Location: {{ location }}</p>
                <p class="text-sm text-gray-500">Positions: {{positions}}</p>
              </div>
            </div>
          </template>
        </Menu>
        <div class="flex flex-col">
          <span class="text-gray-700 dark:text-[#C7CACF] font-semibold text-base leading-tight">{{ company }}</span>
        </div>
      </div>
      <!-- Job Title and Info -->
      <div class="flex flex-2 flex-col gap-2 mt-2">
        <h2 class="text-mdI font-bold text-[#444F60] dark:text-[#C7CACF]">{{ title }}</h2>
        <div class="flex flex-col gap-3 text-sm text-gray-600 dark:text-[#C7CACF]">
          <span class="flex items-center gap-1 text-xs">
            <img :src="sectorIcon" alt="Sector" class="w-4 h-4" />
            {{ sector }}
          </span>
          <span class="flex items-center gap-1 text-xs">
            <svg class="w-4 h-4 text-[#009688]" fill="currentColor" viewBox="0 0 20 20"><path d="M4 3a1 1 0 000 2h12a1 1 0 100-2H4zm0 4a1 1 0 000 2h12a1 1 0 100-2H4zm0 4a1 1 0 000 2h12a1 1 0 100-2H4zm0 4a1 1 0 000 2h12a1 1 0 100-2H4z" /></svg>
            {{ category }}
          </span>
            <span class="flex items-center gap-1 text-xs">
              <img :src="locationIcon" alt="Location" class="w-4 h-4" />
              {{ location }}
            </span>
            <span class="flex items-center gap-1 text-xs">
              <svg class="w-4 h-4 text-[#009688]" fill="currentColor" viewBox="0 0 20 20"><path d="M6 2a1 1 0 00-1 1v2a1 1 0 001 1h8a1 1 0 001-1V3a1 1 0 00-1-1H6zm0 6a1 1 0 00-1 1v8a1 1 0 001 1h8a1 1 0 001-1V9a1 1 0 00-1-1H6z" /></svg>
              {{ experience }}
            </span>
            <span class="flex items-center gap-1 text-xs">
              <svg class="w-4 h-4 text-[#009688]" fill="currentColor" viewBox="0 0 20 20"><path d="M13 7a3 3 0 11-6 0 3 3 0 016 0zm-3 5a7 7 0 00-6.938 6h13.876A7 7 0 0010 12z" /></svg>
              {{ positions }}
            </span>
        </div>
      </div>
    </div>
    <!-- Full Time Badge -->
    <div class="flex items-center gap-2 mt-2">
      <span class="bg-[#009688] text-white text-xs font-semibold px-3 py-1 rounded-full flex items-center gap-1">
        <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20"><path d="M10 2a8 8 0 100 16 8 8 0 000-16zm1 12H9v-2h2v2zm0-4H9V7h2v3z" /></svg>
        {{ type }}
      </span>
    </div>

    <hr class="border-t border-gray-300 my-2" />
    <!-- Job Summary -->
    <div class="text-gray-600 text-center font-semibold text-sm line-clamp-3 dark:text-[#C7CACF]">
      {{ summary }}
    </div>
    <!-- Buttons -->
    <div class="flex gap-3 mt-2 justify-center">
      <button class="border border-[#009688] text-[#009688] font-semibold rounded-md px-5 py-2 hover:bg-teal-50 transition cursor-pointer">Read More</button>
      <button class="bg-[#009688] text-white font-semibold rounded-md px-5 py-2 hover:bg-teal-700 transition cursor-pointer">Apply Now</button>
    </div>
    <!-- Footer -->
    <div class="flex items-center justify-between mt-2 text-xs text-gray-400">
      <span class="flex items-center gap-1">
        <svg data-v-ccf21bcf="" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true" data-slot="icon" class="w-4 md:w-5"><path stroke-linecap="round" stroke-linejoin="round" d="M2.036 12.322a1.012 1.012 0 0 1 0-.639C3.423 7.51 7.36 4.5 12 4.5c4.638 0 8.573 3.007 9.963 7.178.07.207.07.431 0 .639C20.577 16.49 16.64 19.5 12 19.5c-4.638 0-8.573-3.007-9.963-7.178Z"></path><path stroke-linecap="round" stroke-linejoin="round" d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"></path></svg>
        {{ views }}
      </span>
      <button class="hover:text-[#009688] transition">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true" data-slot="icon" class="w-5 h-5 md:w-6 md:h-6 outlineReactiveIcon" data-v-ccf21bcf=""><path stroke-linecap="round" stroke-linejoin="round" d="M7.217 10.907a2.25 2.25 0 1 0 0 2.186m0-2.186c.18.324.283.696.283 1.093s-.103.77-.283 1.093m0-2.186 9.566-5.314m-9.566 7.5 9.566 5.314m0 0a2.25 2.25 0 1 0 3.935 2.186 2.25 2.25 0 0 0-3.935-2.186Zm0-12.814a2.25 2.25 0 1 0 3.933-2.185 2.25 2.25 0 0 0-3.933 2.185Z"></path></svg>
      </button>
    </div>
  </div>
</template>

