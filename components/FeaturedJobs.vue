<script>
import { JobCard } from "#components";

export default {
  components: { JobCard },
  data() {
    return {
      jobs: [
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
          sector: "Finance",
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
      ],
    };
  },
};
</script>

<template>
  <div class="container mx-auto px-4 py-8 overflow-x-hidden">
    <!-- Featured Jobs Section -->
    <section class="flex flex-col items-center">
      <h1 class="text-3xl md:text-4xl font-bold text-gray-700 mb-2 text-center">
        Featured Jobs
      </h1>
      <p class="text-sm font-medium text-gray-600 mb-8 text-center">
        Explore our handpicked selection of top job openings. Find your dream
        career match today.
      </p>
      <div class="">
        <UCarousel
          v-slot="{ job }"
          dots
          loop
          :items="jobs"
          :autoplay="{ delay: 3000 }"
          :ui="{ 
            container: 'gap-[20px] align-items-center',
            dot: 'w-2 h-1 gap-0 bg-[#777] ',
            dots: 'ml-22 mt-5',

          }"
          class="w-full max-w-xs "
        >
          <JobCard v-bind="job" />
        </UCarousel>
      </div>
    </section>
  </div>
</template>
