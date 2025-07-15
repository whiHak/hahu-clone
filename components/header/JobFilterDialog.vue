<script setup lang="ts">
import { Dialog, DialogPanel, TransitionRoot } from "@headlessui/vue";
import { computed, ref } from "vue";

interface Category {
  name: string;
  icon: string;
  positions: number;
  description?: string;
}

const emit = defineEmits(["update:modelValue"]);

const props = defineProps<{
  modelValue: boolean;
  categories: Category[];
}>();

const openModal = computed({
  get() {
    return props.modelValue;
  },
  set(value) {
    emit("update:modelValue", value);
  },
});
</script>

<template>
  <TransitionRoot
    :show="openModal"
    as="template"
    enter="duration-800 ease-out"
    enter-from="opacity-0"
    enter-to="opacity-100"
    leave="duration-200 ease-in"
    leave-from="opacity-100"
    leave-to="opacity-0"
  >
    <Dialog
      as="div"
      class="fixed inset-0 mx-auto w-full md:w-11/12 flex items-center justify-center bg-opacity-30"
      @close="openModal = false"
    >
    <div class="fixed inset-0 backdrop-blur-xs" aria-hidden="true" />
      <DialogPanel
        class="relative overflow-y-auto bg-white dark:bg-[#1B2637] rounded-2xl shadow-2xl w-full p-8 flex flex-col max-h-full"
      >
        <div class="flex justify-between items-center mb-6">
          <div class="flex gap-2 md:gap-4 items-center">
            <Icon
              name="mdi:close"
              class="w-8 h-8 p-3 hover:bg-[#009688] rounded-full cursor-pointer"
              @click="openModal = false"
            />
            <h2
              class="text-sm md:text-md lg:text-lg font-bold text-gray-800 dark:text-white"
            >
              Jobs by sector
            </h2>
          </div>
          <div class="flex items-center gap-4">
            <button
              class="border border-[#009688] text-[#009688] hover:text-white font-semibold rounded-md px-5 py-2 flex items-center gap-1 md:gap-2 hover:bg-[#009688] transition text-xs md:text-md cursor-pointer"
            >
              View All
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                aria-hidden="true"
                data-slot="icon"
                class="w-5 h-5"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M17.25 8.25 21 12m0 0-3.75 3.75M21 12H3"
                ></path>
              </svg>
            </button>
          </div>
        </div>
        <div
          class="w-full gap-3 xl:w-full mx-auto grid grid-cols-1 md:grid-cols-2 xl:grid-cols-4 xl:grid-flow-col md:gap-x-3 gap-y-6 xl:gap-y-3 2xl:gap-y-3 justify-center xl:grid-rows-4"
        >
          <HeaderCategoryCard
            v-for="(cat, idx) in categories"
            :key="cat.name + idx"
            :category="cat"
          />
          <img
            src="/images/mascot-half.svg"
            alt="Mascot"
            class="w-56 row-span-2"
          />
        </div>
        <div class="flex justify-end">
          <div class="">
            <span
              class="font-body font-light text-xs text-gray-500 dark:text-[#C7CACF]"
            >
              Powered by </span
            ><img
              src="https://www.hahu.jobs/images/Hahu_logo_footer.png"
              alt=""
              class="w-24 pl-6"
            />
          </div>
        </div>
      </DialogPanel>
    </Dialog>
  </TransitionRoot>
</template>
