<script setup lang="ts">
import { useDebounceFn} from '@vueuse/core'

const searchTerms = ref("");
const selectedPosition = ref("");
const selectedSector = ref("");
const selectedCity = ref("");
const router=useRouter()
const route=useRoute()

const debounceFilterState = useDebounceFn(() => {
  let query: any = { ...route.query };
  const activeFilters: string[] = [];

  console.log(searchTerms.value)
  if (searchTerms.value) activeFilters.push('search');
  if (selectedPosition.value) activeFilters.push('pid');
  if (selectedSector.value) activeFilters.push('sid');
  if (selectedCity.value) activeFilters.push('cid');

  query.search = searchTerms.value;
  query.pid = selectedPosition.value;
  query.sid = selectedSector.value;
  query.cid = selectedCity.value;

  router.push({ query });
}, 500);

const updateSearchTerm = (value: string) => {
  searchTerms.value = value;
  console.log(searchTerms.value)
  debounceFilterState();
}
const updateSelectedPosition = (value: string) => {
  selectedPosition.value = value;
  debounceFilterState();
}
const updateSelectedSector = (value: string) => { 
  selectedSector.value = value;
  debounceFilterState();
}
const onUpdateSelectedCity = (value: string) => {
  selectedCity.value = value;
  debounceFilterState();
}

const page = ref(2)
const itemsPerPage = 3;
const updatePage = (value:number) =>{

  let query = {...route.query}
  query.page=value.toString();
  router.push({query})

  console.log(value)
  page.value=value
}

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
      "TVET Level IV in Auto Electrician or in a related field of study with relevant work experience, out of which 2 years in a similar role Duties and Responsibilitie...",
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


// const jobs = ref([{}])

</script>

<template>
  <div class="w-full lg:w-9/12 2xl:w-10/12">
    <!-- Filter -->
   <JobsFilter  @updateSearchTerm="updateSearchTerm" @updateSelectedPosition="updateSelectedPosition" @updateSelectedSector="updateSelectedSector" @updateSelectedCity="onUpdateSelectedCity" />

   <div class="flex flex-col justify-between items-start relative md:top-20 w-full h-max">
      <div class="flex gap-x-2 bg-white dark:bg-[#111827] w-full p-3 rounded-lg">
        <div class="shrink grow-0">
          <img src="/images/business.png" alt="business" class="mt-1">
        </div>
        <div class="flex flex-col">
          <div class="text-nowrap ml-8 text-sm font-extrabold xl:text-lg text-gray-600 dark:text-white md:ml-24 xl:ml-0">Business Jobs</div>
          <div class="text-xs text-gray-700 dark:text-gray-300">
            Aspects of overseeing and supervising business operations. Business sector involvements are Strategic Management , Sales Management, Marketing Management, Public Relations, Operation Management, Supply Chain Management, Procurement Management and Financial & Accounting Management.
          </div>
        </div>
      </div>
       <p class="text-md text-gray-600 mb-5 mt-2 dark:text-gray-400 font-bold">Showing {{ (page - 1) * itemsPerPage + 1 }} to {{ Math.min(page * itemsPerPage, jobs.length) }} of {{ jobs.length }} posts</p>

       <div v-if="jobs.length > 0" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-2 w-full">
          <div v-for="job in jobs.slice((page - 1) * itemsPerPage, page * itemsPerPage)" :key="job.title" class="h-max">
            <LandingJobCard v-bind="job" />
          </div>
        </div>
        
        <div v-else class="flex flex-col justify-between items-center w-full "> 
          <img src="/images/search-not-found.svg" alt="no jobs" class="w-1/3 h-1/3 mt-10">
          <p class="text-2xl text-gray-600 mb-5 ml-1 dark:text-gray-300 font-bold">Sorry, we couldn’t find any match for your search</p>
        </div>

        <div class="flex gap-2 w-full items-center relative sm:top-3 self-center justify-center">
          <Icon name="lucide:arrow-left" class=""  />
          <button @click="page=page-1"  :disabled="page<=1" class="text-sm font-semibold hover:scale-101 hover:font-bold cursor-pointer disabled" :class="page<=1 && 'disabled'">Previous</button>
          <UPagination 
          v-model:page="page" 
          as="div"
          :show-controls="false"
          nextIcon="lucide:" 
          activeColor="warning"
          @update:page="updatePage"
          size="md" 
          :total="jobs.length + 6"
          :ui="{
            root:'',
            next: 'border-0 w-20',
            ellipsis: 'bg-red-500  ',
            item: 'bg-ransparent rounded-[0px] border-[0px]  text-gray-800 hover:bg-transparent cursor-pointer', 
          }"
          class=""
        />
        <button @click="page=page+1" :disabled="page>=2" class="text-sm font-semibold ml-4 hover:scale-101 hover:font-bold cursor-pointer">Next</button>
        <Icon name="lucide:arrow-right" class="" />
        </div>
        
      </div>

  </div>
</template>