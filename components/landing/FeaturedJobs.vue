<script setup lang="ts">
const jobs = ref([
  {
    title: "Senior Auto Electrician",
    company: "Ethiopian Engineering...",
    companyLogo: "/images/job-banner.png",
    sector: "Low and Medium Skilled Worker",
    category: "Auto Mechanical Skilled Worker",
    location: "Addis Ababa",
    experience: "6 years",
    positions: "2 Positions",
    type: "Full Time",
    summary:
      "TVET Level IV in Auto Electrician or in a related field of study with relevant work experience, out of which 2 years in a similar role Duties and Responsibilitie...",
    daysLeft: "3 Days Left",
    views: "10k",
    sectorIcon: "/images/business.png",
    locationIcon: "/images/engineering.svg",
  },
  {
    title: "Finance Manager",
    company: "ABC Finance PLC",
    companyLogo: "/images/job-banner.png",
    sector: "Finance sector",
    category: "Financial Services",
    location: "Addis Ababa",
    experience: "5 years",
    positions: "1 Position",
    type: "Full Time",
    summary:
      "Degree in Finance or related field with 5 years experience in financial management.",
    daysLeft: "5 Days Left",
    views: "2k",
    sectorIcon: "/images/business.png",
    locationIcon: "/images/engineering.svg",
  },
  {
    title: "Senior Auto Electrician",
    company: "Ethiopian Engineering...",
    companyLogo: "/images/job-banner-2.png",
    sector: "Low and Medium Skilled Worker",
    category: "Auto Mechanical Skilled Worker",
    location: "Addis Ababa",
    experience: "6 years",
    positions: "2 Positions",
    type: "Full Time",
    summary:
      "TVET Level IV in Auto Electrician or in a related field of study with relevant work experience, out of which 2 years in a similar role Duties and Responsibilitie...",
    daysLeft: "3 Days Left",
    views: "10k",
    sectorIcon: "/images/business.png",
    locationIcon: "/images/engineering.svg",
  },
  {
    title: "Senior Auto Electrician",
    company: "Ethiopian Engineering...",
    companyLogo: "/images/job-banner-3.jpg",
    sector: "Low and Medium Skilled Worker",
    category: "Auto Mechanical Skilled Worker",
    location: "Addis Ababa",
    experience: "6 years",
    positions: "2 Positions",
    type: "Full Time",
    summary:
      "TVET Level IV in Auto Electrician or in a related field of study with relevant work experience, out of which 2 years in a similar role Duties and Responsibilitie...",
    daysLeft: "3 Days Left",
    views: "10k",
    sectorIcon: "/images/business.png",
    locationIcon: "/images/engineering.svg",
  },
  {
    title: "Senior Auto Electrician",
    company: "Ethiopian Engineering...",
    companyLogo: "/images/job-banner.png",
    sector: "Low and Medium Skilled Worker",
    category: "Auto Mechanical Skilled Worker",
    location: "Addis Ababa",
    experience: "6 years",
    positions: "2 Positions",
    type: "Full Time",
    summary:
      "TVET Level IV in Auto Electrician or in a related field of study with relevant work experience, out of which 2 years in a similar role Duties and Responsibilitie...",
    daysLeft: "3 Days Left",
    views: "10k",
    sectorIcon: "/images/business.png",
    locationIcon: "/images/engineering.svg",
  },
]);
</script>

<template>
  <div class="sm:container mx-auto px-4 py-8 overflow-x-hidden">
    <!-- Featured Jobs Section -->
    <section class="flex flex-col items-center">
      <h1
        class="text-3xl md:text-4xl font-bold text-gray-700 dark:text-white mb-7 text-center"
      >
        Featured Jobs
      </h1>
      <p
        class="text-sm font-medium text-gray-600 mb-8 text-center dark:text-[#C7CACF]"
      >
        Explore our handpicked selection of top job openings. Find your dream
        career match today.
      </p>
      <div class="relative rounded-2xl overflow-hidden">
        <div
          class="absolute inset-y-0 left-0 w-70 bg-gradient-to-r from-[#ECEDEF] dark:from-[#02201D] to-transparent z-100 pointer-events-none"
        ></div>
        <div
          class="absolute inset-y-0 right-0 w-70 bg-gradient-to-l from-[#ECEDEF] dark:from-[#02201D] to-transparent z-100 pointer-events-none"
        ></div>
        <UCarousel
          v-slot="{ item: job }"
          dots
          loop
          :items="jobs"
          :autoplay="{ delay: 3000 }"
          :ui="{
            dot: 'w-2 h-1 gap-0 bg-[#777]',
            dots: 'mb-5',
            item: 'basis-1/4',
          }"
          class="w-full max-w-full gap-[20px] relative z-0"
        >
          <LandingJobCard v-bind="job" />
        </UCarousel>
      </div>
    </section>
  </div>
</template>
