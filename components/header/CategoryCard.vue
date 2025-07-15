<script setup lang="ts">
import { defineProps } from "vue";

interface Category {
  name: string;
  icon: string;
  positions: number;
  description?: string;
  link?: string;
}
const router = useRouter()

defineProps<{
  category: Category;
  toggleModal: () => void;
}>();
</script>

<template>
  <NuxtLink :to="category.link" @click="navigateTo(category.link); toggleModal()">
    <div
      class="relative flex items-center justify-center p-4 transition cursor-pointer group min-h-[120px] bg-[#F1F1F1] hover:bg-[#E6F7F5] dark:bg-[#F7F9FA]/[0.01]"
    >
      <div class="flex items-center gap-1">
        <img
          :src="category.icon"
          :alt="category.name"
          class="w-5 h-5 mr-2 object-cover"
        />
        <div class="flex flex-col">
          <div class="flex gap-2 items-center flex-1">
            <span class="font-bold text-md text-gray-800 dark:text-white">{{
              category.name
            }}</span>
            <span class="text-[#009688] font-semibold text-sm">{{
              category.positions
            }}</span>
          </div>
          <div class="text-gray-500 dark:text-[#C7CACF] text-xs line-clamp-2">
            {{ category.description }}
          </div>
        </div>
        <span class="">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            aria-hidden="true"
            data-slot="icon"
            class="w-5 h-5 group-hover:text-primary text-transparent"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M17.25 8.25 21 12m0 0-3.75 3.75M21 12H3"
            ></path>
          </svg>
        </span>
      </div>
    </div>
  </NuxtLink>
</template>
