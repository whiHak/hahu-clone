<script setup lang="ts">
import { ref } from "vue";

const News = ref([
  {
    name: "Natural Science Natural Science",
    icon: "/images/news-6.png",
    description:
      "HaHuJobs offers digital career profiling, job application and subscription based relevant vacancy announcement notifications to job seekers that sign up on its primary service deployment.",
  },
  {
    name: "Business Natural Science",
    icon: "/images/news-45.jpeg",
    description:
      "HaHuJobs offers digital career profiling, job application and subscription based relevant vacancy announcement notifications to job seekers that sign up on its primary service deployment.",
  },
  {
    name: "Creative Arts Natural Science",
    icon: "/images/news-2.jpeg",
    description:
      "HaHuJobs offers digital career profiling, job application and subscription based relevant vacancy announcement notifications to job seekers that sign up on its primary service deployment.",
  },
  {
    name: "Natural Science Natural Science",
    icon: "/images/news-6.png",
    description:
      "HaHuJobs offers digital career profiling, job application and subscription based relevant vacancy announcement notifications to job seekers that sign up on its primary service deployment.",
  },
  {
    name: "Business Natural Science",
    icon: "/images/newsjpeg.jpeg",
    description:
      "HaHuJobs offers digital career profiling, job application and subscription based relevant vacancy announcement notifications to job seekers that sign up on its primary service deployment.",
  },
  {
    name: "Creative Arts Natural Science",
    icon: "/images/news-2.jpeg",
    description:
      "HaHuJobs offers digital career profiling, job application and subscription based relevant vacancy announcement notifications to job seekers that sign up on its primary service deployment.",
  },
  {
    name: "Natural Science Natural Science",
    icon: "/images/news-6.png",
    description:
      "HaHuJobs offers digital career profiling, job application and subscription based relevant vacancy announcement notifications to job seekers that sign up on its primary service deployment.",
  },
  {
    name: "Business Natural Science",
    icon: "/images/newsjpeg.jpeg",
    description:
      "HaHuJobs offers digital career profiling, job application and subscription based relevant vacancy announcement notifications to job seekers that sign up on its primary service deployment.",
  },
  {
    name: "Creative Arts Natural Science",
    icon: "/images/news-7.jp",
    description:
      "HaHuJobs offers digital career profiling, job application and subscription based relevant vacancy announcement notifications to job seekers that sign up on its primary service deployment.",
  },
]);
</script>

<template>
  <div class="container mx-auto px-4 py-8">
    <section class="flex flex-col items-center">
      <h1
        class="text-3xl md:text-4xl font-extrabold text-gray-700 mb-10 dark:text-white text-center"
      >
        News & Events
      </h1>
      <div class=" container overflow-hidden">
        <UCarousel
          v-slot="{ item: news }"
          dots
          :items="News"
          :ui="{
            container: 'gap-[20px] w-full',
            dot: '',
            dots: '',
            item: 'basis-1/3',
          }"
          class="w-full mx-auto"
        >
          <div class="bg-white dark:bg-[#1B2637] rounded-xl min-h-[630px] md:min-h-[570px] xl:min-h-[620px] 2xl:max-w-[360px] border-2 border-gray-100 dark:border-[#1B2637] hover:border-[#009688] shadow-md flex flex-col items- text- hover:shadow-lg transition cursor-pointer">
            <img :src="news.icon" :alt="news.name" class="w-full h-50 mb-4 min-h-[300px] rounded-t-xl object-cover" />
            <div class="px-6 flex flex-col gap-3 items-start justify-between h-full">
                <span class="bg-[#6EC8C0] text-[#333] text-xs rounded-full self-start px-3 py-1 font-semibold flex items-center transition cursor-pointer">
                    HaHu Jobs News
                </span>
                <p class="text-gray-500 dark:text-[#C7CACF] text-xs">3 Nov 2024</p>
                <h2 class="text-xl font-extrabold text-[#333] dark:text-white mb-2 line-clamp-1">{{ news.name }}</h2>
                <p class="text-gray-600 dark:text-[#C7CACF] text-sm text-wrap w-60">{{ news.description }}</p>
                <button class="bg-teal-600 hover:bg-teal-700 text-white text-sm self-center rounded-md px-5 py-1 font-semibold flex items-center gap-2 transition cursor-pointer">
                    Read more
                    <span class="text-xl">→</span>
                </button>
            </div>
          </div>
        </UCarousel>
      </div>
    </section>
  </div>
</template>
