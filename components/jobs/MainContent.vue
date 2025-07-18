<script setup lang="ts">

const searchTerms = ref("");
const selectedPosition = ref("");
const selectedSector = ref("");
const selectedCity = ref("");
const router=useRouter()
const route=useRoute()


const updateSearchTerm = (value: string) => {
  searchTerms.value = value;
  router.push({
    query: {
      ...route.query,
      search: searchTerms.value
    }
  })
}
const updateSelectedPosition = (value: string) => {
  selectedPosition.value = value;
  router.push({
    query: {
      ...route.query,
      position: selectedPosition.value
    }
  })
}
const updateSelectedSector = (value: string) => { 
  selectedSector.value = value;
}
const onUpdateSelectedCity = (value: string) => {
  selectedCity.value = value;
}


// const jobs = ref([
//   {
//     title: "Senior Auto Electrician",
//     company: "Ethiopian Engineering...",
//     companyLogo: "/images/job-banner.png",
//     sector: "Low and Medium Skilled Worker",
//     category: "Auto Mechanical Skilled Worker",
//     location: "Addis Ababa",
//     experience: "6 years",
//     positions: "2 Positions",
//     type: "Full Time",
//     summary:
//       "TVET Level IV in Auto Electrician or in a related field of study with relevant work experience, out of which 2 years in a similar role Duties and Responsibilitie...",
//     daysLeft: "3 Days Left",
//     views: "10k",
//     sectorIcon: "/images/business.png",
//     locationIcon: "/images/engineering.svg",
//   },
//   {
//     title: "Finance Manager",
//     company: "ABC Finance PLC",
//     companyLogo: "/images/job-banner.png",
//     sector: "Finance sector",
//     category: "Financial Services",
//     location: "Addis Ababa",
//     experience: "5 years",
//     positions: "1 Position",
//     type: "Full Time",
//     summary:
//       "TVET Level IV in Auto Electrician or in a related field of study with relevant work experience, out of which 2 years in a similar role Duties and Responsibilitie...",
//     daysLeft: "5 Days Left",
//     views: "2k",
//     sectorIcon: "/images/business.png",
//     locationIcon: "/images/engineering.svg",
//   },
//   {
//     title: "Senior Auto Electrician",
//     company: "Ethiopian Engineering...",
//     companyLogo: "/images/job-banner-2.png",
//     sector: "Low and Medium Skilled Worker",
//     category: "Auto Mechanical Skilled Worker",
//     location: "Addis Ababa",
//     experience: "6 years",
//     positions: "2 Positions",
//     type: "Full Time",
//     summary:
//       "TVET Level IV in Auto Electrician or in a related field of study with relevant work experience, out of which 2 years in a similar role Duties and Responsibilitie...",
//     daysLeft: "3 Days Left",
//     views: "10k",
//     sectorIcon: "/images/business.png",
//     locationIcon: "/images/engineering.svg",
//   },
//   {
//     title: "Senior Auto Electrician",
//     company: "Ethiopian Engineering...",
//     companyLogo: "/images/job-banner-3.jpg",
//     sector: "Low and Medium Skilled Worker",
//     category: "Auto Mechanical Skilled Worker",
//     location: "Addis Ababa",
//     experience: "6 years",
//     positions: "2 Positions",
//     type: "Full Time",
//     summary:
//       "TVET Level IV in Auto Electrician or in a related field of study with relevant work experience, out of which 2 years in a similar role Duties and Responsibilitie...",
//     daysLeft: "3 Days Left",
//     views: "10k",
//     sectorIcon: "/images/business.png",
//     locationIcon: "/images/engineering.svg",
//   },
//   {
//     title: "Senior Auto Electrician",
//     company: "Ethiopian Engineering...",
//     companyLogo: "/images/job-banner.png",
//     sector: "Low and Medium Skilled Worker",
//     category: "Auto Mechanical Skilled Worker",
//     location: "Addis Ababa",
//     experience: "6 years",
//     positions: "2 Positions",
//     type: "Full Time",
//     summary:
//       "TVET Level IV in Auto Electrician or in a related field of study with relevant work experience, out of which 2 years in a similar role Duties and Responsibilitie...",
//     daysLeft: "3 Days Left",
//     views: "10k",
//     sectorIcon: "/images/business.png",
//     locationIcon: "/images/engineering.svg",
//   },
// ]);

const jobs = ref([{}])

</script>

<template>
  <div class="w-full lg:w-9/12 2xl:w-10/12 ">
    <h1 v-if="searchTerms?.length > 0" class="h-56">{{searchTerms}}</h1>
    <!-- Filter -->
   <JobsFilter  @updateSearchTerm="updateSearchTerm" @updateSelectedPosition="updateSelectedPosition" @updateSelectedSector="updateSelectedSector" @updateSelectedCity="onUpdateSelectedCity" />

   <div class="flex flex-col justify-between items-start relative md:top-20 w-full"> 
       <p class="text-md text-gray-600 mb-5 ml-1 dark:text-gray-400 font-bold">Showing {{jobs.length - 1}} of 285 posts</p>

       <div v-if="jobs.length > 1" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-2 w-full">
           <div v-for="job in jobs" class="">
            <LandingJobCard v-bind="job" />
           </div>
       </div>
       
      <div v-else class="flex flex-col justify-between items-center w-full "> 
        <img src="/images/search-not-found.svg" alt="no jobs" class="w-1/3 h-1/3 mt-10">
        <p class="text-2xl text-gray-600 mb-5 ml-1 dark:text-gray-300 font-bold">Sorry, we couldn’t find any match for your search</p>
      </div>

   </div>

  </div>
</template>