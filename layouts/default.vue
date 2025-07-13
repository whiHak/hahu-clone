<script setup lang="ts">
import { mobNavigation, navigation } from "~/constants";
import { ref, computed } from 'vue';
import { useRoute } from 'vue-router';
import { Dialog, DialogOverlay, DialogPanel } from '@headlessui/vue';

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
console.log(route.fullPath);
const isActive = (href: string) => route.path === href; 
</script>
<template>
  <div class="min-h-screen flex flex-col text-[#697280] bg-[#ECEDEF] dark:bg-[#02201D] ">
    <!-- Navigation -->
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
          class="hidden md:flex w-full items-center justify-end space-x-6 mx-6"
        >
          <NuxtLink
            v-for="item in navigation"
            :key="item.href"
            :to="item.href"
            :class="isActive(item.href) ? 'nav-link text-sm font-semibold transition-colors text-[#009688]  dark:text-white' : 'nav-link text-sm font-[400] transition-colors dark:text-white'"
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
                    v-for="item in navigation" 
                    :key="item.href" 
                    :to="item.href"
                    :class="isActive(item.href) ? 'nav-link text-lg font-semibold transition-colors text-[#009688] border-l-4 border-[#009688] pl-2' : 'nav-link text-lg font-[400] transition-color border-l-4 border-[#009688] pl-2'"
                    @click="isMobileMenuOpen = false"
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
    </header>


    <!-- Main Content -->
    <main class="flex-1">
      <slot />
    </main>

  </div>
  <!-- Footer outside the root div to avoid missing end tag error -->
  <footer class="w-full mt-16  font-sans">
    <div class="container flex flex-wrap justify-between items-start px-16 py-2 gap-10">
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
      <div class="flex flex-col min-w-[120px] md:min-w-[320px] max-w-[420px] items-start">
        <img src="/images/minab-logo.png" alt="Minab Logo" class="w-[90px] mb-2" />
        <p class="text-gray-700 dark:text-white text-sm mt-1 font-medium text-wrap w-60 md:w-120 leading-relaxed">
          HaHuJobs is a cloud based product owned and manged by a technology consulting firm called Minab IT solutions PLC. Minab was founded in 2014 and has an extensive experience in software development for the past nine years.
        </p>
      </div>
      <div class="flex flex-col min-w-[220px] items-end">
        <div class="text-base text-gray-700 dark:text-white  mb-1">Powered by</div>
        <img src="/logo_dark_2.svg" alt="HaHuJobs Logo" class="w-[140px] mb-1" />
        <div class="flex gap-2">
          <p class="text-teal-500 text-lg font-semibold">ለሀገር ልጅ </p>
          <p class="text-lg font-semibold dark:text-white">በሀገር!</p>
        </div>
      </div>
    </div>
    <div class="container flex flex-wrap justify-between items-center border-t pt-10 border-gray-400 px-16 py-4 mt-2">
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
