<script setup lang="ts">
import { mobNavigation, navigation } from "~/constants";
import { ref, computed } from 'vue';
import { useRoute } from 'vue-router';
import { Dialog, DialogOverlay, DialogPanel } from '@headlessui/vue';

const isMobileMenuOpen = ref(false); // Start with the menu closed

function setIsOpen(value: any) {
    isMobileMenuOpen.value = value
}

type Theme = "light" | "dark";

const colorMode = useColorMode();
const isDark = computed(() => colorMode.value === "dark");

const toggleTheme = (newTheme: Theme) => {
  console.log("Preference before toggle:", useColorMode().preference);
  useColorMode().preference = newTheme
};

const route = useRoute();
console.log(route);
// const isActive = (href: string) => route.path === href; 
</script>
<template>
  <div class="min-h-screen flex flex-col text-[#697280] bg-[#ECEDEF] dark:bg-[#02201D] ">
    <!-- Navigation -->
    <header
      class="header sticky top-0 z-101 w-full backdrop-blur "
    >
      <nav class="container flex h-16 items-center px-4">
        <!-- Logo -->
        <NuxtLink to="/" class="flex items-center gap-2 font-bold text-xl">
            <img :src="isDark?'/logo_dark_1.svg':'/logo_dark_2.svg'" alt="Logo" class="w-40">
        </NuxtLink>

        <!-- Desktop Navigation -->
        <div
          class="hidden md:flex w-full items-center justify-end space-x-6 mx-6"
        >
          <NuxtLink
            v-for="item in navigation"
            :key="item.href"
            :to="item.href"
            class="nav-link text-sm font-[400] transition-colors hover:text-[#6EC8C0] dark:text-white"
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
              class="h-4 w-4 dark:text-[#C7CACF]"
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
              <Icon :name="isMobileMenuOpen ? 'lucide:x' : 'lucide:menu'" class="h-6 w-6" />
            </button>
          </div>
          <!-- Mobile Navigation Dialog -->
          <Dialog :open="isMobileMenuOpen"  @close="setIsOpen" class="fixed text-[#697280] w-full inset-0 z-50 md:hidden">
            <div class="flex items-center justify-center h-full">
              <DialogPanel class="absolute top-15 w-full  backdrop-blur-lg rounded-lg p-6">
                <nav class="container grid gap-y-4 py-2 ">
                  <NuxtLink 
                    v-for="item in navigation" 
                    :key="item.href" 
                    :to="item.href"
                    class="text-lg font-[400] hover:text-primary"
                    @click="isMobileMenuOpen = false"
                  >
                    {{ item.name }}
                  </NuxtLink>
                  <!-- separator line -->
                    <hr class="border-t border-gray-300 my-4" />
                  <NuxtLink 
                    v-for="item in mobNavigation" 
                    :key="item.href" 
                    :to="item.href"
                    class="text-lg font-[400]  hover:text-primary"
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

    <!-- Footer -->
    <footer></footer>

  </div>
</template>
