<script setup lang="ts">
import { useDebounceFn } from '@vueuse/core'
const isOpen = ref(true);
const value = ref([0, 3]);

const isMaxYoe = ref(false);
const isBidActive = ref(false);
const isContractActive = ref(false);
const isFullTimeActive = ref(false);
const isInternshipActive = ref(false);
const isPartTimeActive = ref(false);

const route = useRoute();
const router = useRouter();
const debouncedFilterState = useDebounceFn(() => {
  let query: any = { ...route.query };
  const activeFilters: string[] = [];

  // Add to activeFilters if active
  if (isBidActive.value) activeFilters.push('bid');
  if (isContractActive.value) activeFilters.push('contract');
  if (isFullTimeActive.value) activeFilters.push('full-time');
  if (isInternshipActive.value) activeFilters.push('internship');
  if (isPartTimeActive.value) activeFilters.push('part-time');

  // Set the query.t based on active filters
  query.t = activeFilters.length > 0 ? activeFilters.join(',') : undefined;

  // Delete min and max yoe if isMaxYoe is true
  if (isMaxYoe.value) {
    delete query.min_yoe;
    delete query.max_yoe;
    query.max_yoe_gt = 'true';
  } else {
    if (value.value) {
      delete query.max_yoe_gt;
      query.min_yoe = value.value[0].toString();
      query.max_yoe = value.value[1].toString();
    }
  }

  if (!isMaxYoe.value) delete query.max_yoe_gt;

  console.log(query);
  router.push({ query });
}, 1000);

const filterState = computed(() => ({ 
  isBidActive: isBidActive.value,
  isContractActive: isContractActive.value,
  isFullTimeActive: isFullTimeActive.value,
  isInternshipActive: isInternshipActive.value,
  isPartTimeActive: isPartTimeActive.value,
  isMaxYoe: isMaxYoe.value,
  value: value.value,
}));

watch(filterState, debouncedFilterState);

</script>

<template>
  <div
    class="xs:sticky lg:top-28 h-fit lg:w-3/12 2xl:w-2/10 px-4 lg:pr-8 lg:pl-2 mt-20 lg:mt-2 md:mx-16 lg:mx-0"
  >
    <UCollapsible
      :open="isOpen"
      :unmount-on-hide="false"
      class="flex flex-col gap-3"
    >
      <div class="flex">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          aria-hidden="true"
          data-slot="icon"
          class="w-5 md:w-6 mr-4 text-gray-600 dark:text-gray-300"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M6 13.5V3.75m0 9.75a1.5 1.5 0 0 1 0 3m0-3a1.5 1.5 0 0 0 0 3m0 3.75V16.5m12-3V3.75m0 9.75a1.5 1.5 0 0 1 0 3m0-3a1.5 1.5 0 0 0 0 3m0 3.75V16.5m-6-9V3.75m0 3.75a1.5 1.5 0 0 1 0 3m0-3a1.5 1.5 0 0 0 0 3m0 9.75V10.5"
          ></path>
        </svg>
        <UButton
          label="Additional Filters"
          as="div"
          color="neutral"
          size="md"
          :trailing-icon="
            isOpen ? 'i-lucide-chevron-up' : 'i-lucide-chevron-down'
          "
          class="text-sm text-gray-700 dark:text-gray-400"
          block
          @click="isOpen = !isOpen"
          :ui="{
            base: 'border-0 bg-transparent font-bold outline-0 cursor-pointer hover:bg-transparent',
            trailingIcon: 'text-[#009688] text-lg',
          }"
        />
      </div>

      <template #content>
        <!-- Slider -->
        <USlider
          v-model="value"
          :min-steps-between-thumbs="1"
          :step="1"
          :min="0"
          :disabled="isMaxYoe"
          as="div"
          :disable-closing-trigger="true"
          :max="10"
          :ui="{
            range: 'bg-[#009688] dark:bg-gray-700',
            track: 'bg-gray-400 w-full dark:bg-gray-700',
            thumb:
              'bg-[#009688] dark:bg-gray-300 rounded-full ring-0 active:ring-0 focus-visible:outline-0 focus:ring-0',
            root: 'py-2',
          }"
        />
        <div class="flex items-center justify-between">
          <p class="text-xs text-gray-500 dark:text-gray-400">
            0 - 3 Years of Experience
          </p>
          <UCheckbox
            v-model="isMaxYoe"
            label="> 10"
            default-value
            size="lg"
            :ui="{
              base: 'border-1 border-[#009688]',
              icon: 'bg-[#009688]',
            }"
          />
        </div>
        <hr
          class="my-5 mx-auto w-40 self-center border-gray-300 dark:border-gray-700"
        />
        <!-- Type-->
        <p class="text-sm font-bold text-gray-900 dark:text-gray-400 mb-3">
          Type
        </p>
        <div class="flex flex-wrap gap-2">
          <UButton
            label="Bid"
            :trailing-icon="isBidActive ? 'i-lucide-x' : 'i-lucide-plus'"
            size="xs"
            :ui="{
              base: 'border-1 border-[#009688] bg-transparent font-[400] text-gray-500 text-sm rounded-full  hover:bg-[#E6F7F5] py-[1px] cursor-pointer',
              trailingIcon: 'text-xs -ml-[2px]'
            }"
            :class="isBidActive && 'bg-[#009688] hover:bg-[#009688] text-gray-800'"
            @click="isBidActive = !isBidActive"
          />
          <UButton
            label="Contract"
            :trailing-icon="isContractActive ? 'i-lucide-x' : 'i-lucide-plus'"
            size="xs"
            :ui="{
              base: 'border-1 border-[#009688] bg-transparent font-[400] text-gray-500 text-sm rounded-full  hover:bg-[#E6F7F5] py-[1px] cursor-pointer',
              trailingIcon: 'text-xs -ml-[2px]'
            }"
            :class="isContractActive && 'bg-[#009688] hover:bg-[#009688] text-gray-800'"
            @click="isContractActive = !isContractActive"
          />
          <UButton
            label="Full Time"
            :trailing-icon="isFullTimeActive ? 'i-lucide-x' : 'i-lucide-plus'"
            size="xs"
            :ui="{
              base: 'border-1 border-[#009688] bg-transparent font-[400] text-gray-500 text-sm rounded-full  hover:bg-[#E6F7F5] py-[1px] cursor-pointer',
              trailingIcon: 'text-xs -ml-[2px]'
            }"
            :class="isFullTimeActive && 'bg-[#009688] hover:bg-[#009688] text-gray-800'"
            @click="isFullTimeActive = !isFullTimeActive"
          />
          <UButton
            label="Internship"
            :trailing-icon="isInternshipActive ? 'i-lucide-x' : 'i-lucide-plus'"
            size="xs"
            :ui="{
              base: 'border-1 border-[#009688] bg-transparent font-[400] text-gray-500 text-sm rounded-full  hover:bg-[#E6F7F5] py-[1px] cursor-pointer',
              trailingIcon: 'text-xs -ml-[2px]'
            }"
            :class="isInternshipActive && 'bg-[#009688] hover:bg-[#009688] text-gray-800'"
            @click="isInternshipActive = !isInternshipActive"
          />
          <UButton
            label="Part Time"
            :trailing-icon="isPartTimeActive ? 'i-lucide-x' : 'i-lucide-plus'"
            size="xs"
            :ui="{
              base: 'border-1 border-[#009688] bg-transparent font-[400] text-gray-500 text-sm rounded-full  hover:bg-[#E6F7F5] py-[1px] cursor-pointer',
            }"
            :class="isPartTimeActive && 'bg-[#009688] hover:bg-[#009688] text-gray-800'"
            @click="isPartTimeActive = !isPartTimeActive"
          />
        </div>

        <hr
          class="my-8 mx-auto w-40 self-center border-gray-300 dark:border-gray-700"
        />
        <!--Region-->
        <div class="flex items-center justify-start gap-1">
          <p class="text-sm font-bold text-gray-900 dark:text-gray-400">
            Region
          </p>
          <Icon
            name="i-lucide-map-pin"
            class="text-gray-500 dark:text-gray-400 text-xs"
          />
        </div>
        <!--Ethiopia Maop-->
        <img
          src="/ethiopia.svg"
          alt="Ethiopia"
          class="w-full h-full text-[#009688] mt-5"
        />

        <UButton
          label="All"
          size="md"
          :ui="{
            base: 'bg-[#009688] text-gray-300 font-bold text-xs rounded-full py-[2px] px-2 cursor-pointer',
          }"
        />
      </template>
    </UCollapsible>
  </div>
</template>
