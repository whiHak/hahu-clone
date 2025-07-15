<script setup lang="ts">
import { mobNavigation, navigation } from "~/constants";
import { ref, computed } from 'vue';
import { useRoute } from 'vue-router';
import { Dialog, DialogPanel } from '@headlessui/vue';

const isMobileMenuOpen = ref(false);

function setIsOpen(value: any) {
    isMobileMenuOpen.value = value
}

type Theme = "light" | "dark";

const colorMode = useColorMode();
const isDark = computed(() => colorMode.value === "dark");

const toggleTheme = (newTheme: Theme) => {
  console.log("Preference before toggle:", useColorMode().preference);
  colorMode.preference = newTheme
};

const route = useRoute();
const isActive = (href: string) => route.path === href || route.hash === href; 

const isJobsFilterOpen = ref(false)

const toggleModal = () => {
  isJobsFilterOpen.value = !isJobsFilterOpen.value
}

// Job sectors/categories array for dialog
const jobCategories = ref([
  {
    name: 'Natural Science',
    icon: '/images/engineering.svg',
    positions: 33,
    description: 'Natural science concerned with the description, prediction, and unde...',
    sector: 'Natural Science',
    link: '/jobs?sid=natural-science&page=1'
  },
  {
    name: 'Hospitality',
    icon: '/images/business.png',
    positions: 26,
    description: 'Operations of hotels, restaurants, cruise ships, amusement parks, de...',
    sector: 'Hospitality',
    link: '/jobs?sid=hospitality&page=1'
  },
  {
    name: 'Finance',
    icon: '/images/hahu_featured.svg',
    positions: 168,
    description: 'General management principles to financial resources of the enterpri...',
    sector: 'Finance',
    link: '/jobs?sid=finance&page=1'
  },
  {
    name: 'Manufacturing',
    icon: '/images/downward-arrow.svg',
    positions: 0,
    description: 'Manufacturing is a production sector for all products. This sector c...',
    sector: 'Manufacturing',
    link: '/jobs?sid=manufacturing&page=1'
  },
  {
    name: 'Business',
    icon: '/images/bookmark.png',
    positions: 260,
    description: 'Aspects of overseeing and supervising business operations. Business ...',
    sector: 'Business',
    link: '/jobs?sid=business&page=1'
  },
  {
    name: 'Low and Medium Skilled...',
    icon: '/images/job-type-arrow.svg',
    positions: 59,
    description: 'Does not require completing a college degree or specialized training...',
    sector: 'Low and Medium Skilled...',
    link: '/jobs?sid=low-and-medium-skilled&page=1'
  },
  {
    name: 'Legal Services',
    icon: '/images/keyboard.svg',
    positions: 24,
    description: 'services involving legal or law related matters like issue of legal ...',
    sector: 'Legal Services',
    link: '/jobs?sid=legal-services&page=1'
  },
  {
    name: 'Social Science',
    icon: '/images/news-2.jpeg',
    positions: 32,
    description: 'Social science focus on the study of society and the relationship am...',
    sector: 'Social Science',
    link: '/jobs?sid=social-science&page=1'
  },
  {
    name: 'Creative Arts',
    icon: '/images/news-6.png',
    positions: 23,
    description: 'Human creative skill and imagination, typically in a visual form suc...',
    sector: 'Creative Arts',
    link: '/jobs?sid=creative-arts&page=1'
  },
  {
    name: 'Transportation & Logistics',
    icon: '/images/business.png',
    positions: 29,
    description: 'Involves both internal and external distribution networks which incl...',
    sector: 'Transportation & Logistics',
    link: '/jobs?sid=transportation-and-logistics&page=1'
  },
  {
    name: 'ICT',
    icon: '/images/engineering.svg',
    positions: 45,
    description: 'ICT sector professionals conduct research, plan, design, support ana...',
    sector: 'ICT',
    link: '/jobs?sid=ict&page=1'
  },
  {
    name: 'Education',
    icon: '/images/minab-logo.png',
    positions: 56,
    description: 'Education is about teaching, learning skills and knowledge. The Educ...',
    sector: 'Education',
    link: '/jobs?sid=education&page=1'
  },
  {
    name: 'Engineering',
    icon: '/images/engineering.svg',
    positions: 161,
    description: 'Engineering sector is a career that brings together the technologica...',
    sector: 'Engineering',
    link: '/jobs?sid=engineering&page=1'
  },
  {
    name: 'Health Care',
    icon: '/images/job_application.png',
    positions: 64,
    description: 'Health care enhance quality of life by enhancing health promotion, d...',
    sector: 'Health Care',
    link: '/jobs?sid=health-care&page=1'
  },
]);

</script>

<template>
    <header
      class="sm:container mx-auto  sticky top-0 z-101 w-full backdrop-blur "
    >
      <nav class="flex h-16 items-center px-4">
        <!-- Logo -->
        <NuxtLink to="/" class="flex flex-col text-xl">
            <img :src="isDark?'/logo_dark_1.svg':'/logo_dark_2.svg'" alt="Logo" class="w-40">
            <div class="dark:text-white text-xs ml-0.5 mt-0.5"> Primary </div>
        </NuxtLink>

        <!-- Desktop Navigation -->
        <div
          class="hidden md:flex w-full items-center justify-end space-x-6 mx-6 dark:text-white"
        >
          <NuxtLink
            v-for="(item) in navigation"
            :key="item.href"
            :to="item.name === 'Jobs'? '#' : item.href"
            :target="item.name === 'Contacts' ? '_blank': '_self'"
            :class="isActive(item.href) ? 'nav-link text-sm font-semibold transition-colors text-[#009688]' : 'nav-link text-sm font-[400] transition-colors '"
            @click="item.name === 'Jobs' && route.path !== '/jobs' ? toggleModal() : null"
            > 
            {{ item.name }}
          </NuxtLink>
        </div>

        <div class="flex items-center ml-auto gap-2">
          <!-- Theme Toggle -->
          <button
            class="size-9 flex items-center justify-center rounded-md hover:bg-accent hover:text-accent-foreground cursor-pointer"
            @click="toggleTheme(colorMode.preference === 'dark' ? 'light' : 'dark')"
          >
            <Icon
              :name="isDark ? 'lucide:sun' : 'lucide:moon'"
              class="sm:h-4 sm:w-4 h-6 w-6 dark:text-[#C7CACF]"
            />
          </button>

          <!-- Auth Buttons -->
          <div class="hidden md:flex items-center gap-2 ">
            <NuxtLink
              to="/auth/login"
              class="inline-flex items-center justify-center rounded-md text-xs font-medium bg-[#009688] hover:bg-[#6EC8C0] transition duration-300 h-7 px-2 text-white"
            >
              Login
            </NuxtLink>
            <p class="text-center dark:text-[#C7CACF] align-baseline">or</p>
            <NuxtLink
              to="/auth/register"
              class="inline-flex items-center justify-center text-nowrap  rounded-md text-xs font-medium bg-[#009688] hover:bg-[#6EC8C0] transition duration-300 h-7 px-2 text-white"
            >
              Sign up
            </NuxtLink>
          </div>
          <!-- Mobile Navigation -->
          <div class="flex md:hidden h-16 items-center justify-center">
            <button 
              class="mr-2"
              @click="isMobileMenuOpen = !isMobileMenuOpen"
            >
              <Icon :name="isMobileMenuOpen ? 'lucide:x' : 'lucide:menu'" class="h-7 w-7 dark:text-white" />
            </button>
          </div>
          <!-- Mobile Navigation Dialog -->
          <Dialog :open="isMobileMenuOpen"  @close="setIsOpen" class="fixed text-[#697280] w-full inset-0 z-50 md:hidden">
            <div class="flex items-center justify-center h-full">
              <DialogPanel class="absolute top-15 w-full  backdrop-blur-lg rounded-lg p-6">
                <nav class="grid gap-y-4 py-2 dark:text-white ">
                  <NuxtLink  
                    v-for="(item, index) in navigation" 
                    :key="item.href" 
                    :to="item.name === 'Jobs' ? '#' : item.href"
                    :class="isActive(item.href) ? 'nav-link text-lg font-semibold transition-colors text-[#009688] border-l-4 border-[#009688] pl-2' : 'nav-link text-lg font-[400] transition-color border-l-4 border-[#009688] pl-2'"
                    @click="isMobileMenuOpen = false; item.name === 'Jobs' ? toggleModal() : null" 
                  >
                    {{ item.name }}
                  </NuxtLink>
                    <hr class="border-t border-gray-300 my-4 w-full" />
                  <NuxtLink 
                    v-for="item in mobNavigation" 
                    :key="item.href" 
                    :to="item.href"
                    :class="isActive(item.href) ? 'nav-link text-lg font-semibold transition-colors text-[#009688] border-l-4 border-[#009688] pl-2' : 'nav-link text-lg font-[400] transition-color border-l-4 border-[#009688] pl-2'"
                    @click="isMobileMenuOpen = false"
                  >
                    {{ item.name }}
                  </NuxtLink>
                </nav>
              </DialogPanel>
            </div>
          </Dialog>
        </div>
      </nav>
      <HeaderJobFilterDialog v-model="isJobsFilterOpen" :categories="jobCategories" :toggleModal="toggleModal" />
    </header>
</template>