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
  <div class=" bg-[#f8fdfc] dark:bg-[#1B2637]">
    <section class="flex flex-col items-center justify-center sm:container mx-auto px-4 py-8">
      <h1
        class="text-3xl md:text-4xl font-extrabold text-gray-700 mb-10 dark:text-white text-center"
      >
        News & Events
      </h1>
      <div class="sm:container overflow-x-hidden h-[670px] sm:h-[650px]">
        <UCarousel
          v-slot="{ item: news, index }"
          :items="News"
          :ui="{
            container: 'gap-[20px] md:w-[980px] h-max align',
            item: 'sm:basis-1/3',
            dots: 'flex gap-2 self-center justify-center',
            dot: 'bg-[#009688] w-3 h-1 rounded-[0px] focus:bg-[#009688] gap-2 self-center justify-center'
          }"
          dots          
          class="w-screen sm:max-w-[1050px] px-5 flex flex-col align-center mx-auto "
        >
          <div class="bg-white dark:bg-[#1B2637] rounded-xl min-h-[630px] md:min-h-[570px] xl:min-h-[620px] 2xl:max-w-[360px] border-2 border-gray-100 dark:border-[#1B2637] hover:border-[#009688] shadow-md flex flex-col items-center text- hover:shadow-lg transition cursor-pointer">
            <img :src="news.icon" :alt="news.name" class="max-w-[360px] md:max-w-[560px] w-full h-50 mb-4 min-h-[300px] rounded-t-xl object-cover" />
            <div class="px-6 flex flex-col gap-3 items-start justify-between h-full max-w-[360px] md:max-w-[560px]">
                <span class="bg-[#6EC8C0] text-[#333] text-xs rounded-full self-start px-3 py-1 font-semibold flex items-center transition cursor-pointer">
                    HaHu Jobs News
                </span>
                <p class="text-gray-500 dark:text-[#C7CACF] text-xs">3 Nov 2024</p>
                <h2 class="text-xl font-extrabold text-[#333] dark:text-white mb-2 line-clamp-1">{{ news.name }}</h2>
                <p class="text-gray-600 dark:text-[#C7CACF] text-sm text-wrap">{{ news.description }}</p>
                <button class="bg-teal-600 hover:bg-teal-700 text-white text-sm md:self-center rounded-md px-5 py-1 font-semibold flex items-center gap-2 transition cursor-pointer mb-5">
                    Read more
                    <span class="text-xl">→</span>
                </button>
            </div>
          </div>
        </UCarousel>
      </div>
      <button class="bg-teal-600 mt-7 hover:bg-teal-700 text-white text-sm rounded-md px-5 py-2 font-semibold flex items-center gap-2 transition cursor-pointer self-center">
          More Blogs
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true" data-slot="icon" class="ml-2 w-4 h-4 md:w-5 md:h-5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 6H5.25A2.25 2.25 0 0 0 3 8.25v10.5A2.25 2.25 0 0 0 5.25 21h10.5A2.25 2.25 0 0 0 18 18.75V10.5m-10.5 6L21 3m0 0h-5.25M21 3v5.25"></path></svg>
        </button>
    </section>
  </div>
</template>
