<script setup lang="ts">
const isSearchOpen = ref(false);
const isPositionFilterOpen = ref(false);
const isSectorFilterOpen = ref(false);
const isCityFilterOpen = ref(false);

const searchTerm = ref("");
const selectedPosition = ref("");
const selectedSector = ref("");
const selectedCity = ref("");



const emit = defineEmits(['updateSearchTerm', 'updateSelectedPosition', 'updateSelectedSector', 'updateSelectedCity'])



</script>

<template>
     <div
      class="lg:w-[72%] 2xl:w-[79%] max-w-[1180px] pb-4 w-full lg:mr-10 xl:fixed z-10 lg:backdrop-blur-md lg:pt-5 flex lg:flex-row flex-col items-center lg:gap-y-4 gap-x-2"
    >
    <!-- Search -->
    <div class="flex flex-col basis-2/4">
        <UInput
          v-model="searchTerm"
          placeholder="Search"
          color="neutral"
          variant="ghost"
          :ui="{
            trailingIcon: 'text-gray-500 ml-2 dark:text-gray-400 ',
            leadingIcon: '',
            base:'focus:rounded-bl-[0px] rounded-r-[0px] text-secondary focus:ring-1 block w-full bg-transparent border-0 focus:border-0 focus:bg-transparent h-10 focus:ring-transparent focus:outline-none text-base dark:placeholder:text-secondary-4 dark:text-secondary-lite placeholder:text-sm placeholder:ml-10',
            root: 'border-0 self-center w-full bg-white  rounded-tl-lg  ',
          }"
          class="hover:ring-1 hover:ring-[#009688] hover:bg-white focus:ring-0 border-1 border-gray-300"
          @focus="isSearchOpen = !isSearchOpen; emit('updateSearchTerm', searchTerm)"
          @blur="isSearchOpen = false ; emit('updateSearchTerm', '')"
          @update:model-value="emit('updateSearchTerm', searchTerm)"
        >
          <template #trailing>
            <UIcon name="i-lucide-x" class="text-gray-500 dark:text-gray-400 ml-2" />
            <UIcon
              name="i-lucide-search"
              class="text-gray-500 dark:text-gray-400 mx-4 hover:text-[#009688] hover:scale-110 transition-all duration-300 cursor-pointer"
            />
          </template>
        </UInput>
        <UCollapsible   
          :open="isSearchOpen"
          :unmount-on-hide="false"
          class="flex flex-col gap-3 md:fixed w-full top-[62px] md:w-[39.2%] "
        >
          <template #content>
            <div class="flex flex-col h-40 overflow-y-auto border-x-[#009688] border-b-[#009688] border-1">
                <div v-for="i in 7" :key="i" class=" text-sm font-bold bg-white pl-2 hover:bg-gray-300 border-b-1 border-gray-300 p-1">
                    {{ "Search Result" }}
                </div>
            </div>
          </template>
        </UCollapsible>
    </div>
    <!-- Position -->
    <div class="flex flex-col basis-1/4">
        <UButton
          :label="selectedPosition ? selectedPosition : 'Select Position'"
          as="div"
          color="neutral"
          variant="subtle"
          size="md"
          :trailing-icon="
            isPositionFilterOpen ? 'i-lucide-chevron-up' : 'i-lucide-chevron-down'
          "
          class="text-xs text-gray-500 dark:text-gray-400 bg-white hover:bg-white hover:ring-1 hover:ring-[#009688] "
          block
          @click="isPositionFilterOpen = !isPositionFilterOpen; emit('updateSelectedPosition', selectedPosition)"
          :ui="{
            base: ' bg-transparent py-[11px] rounded-[0px]  cursor-pointer',
            trailingIcon: 'text-lg',
          }"
        />
        <UCollapsible
          :open="isPositionFilterOpen"
          :unmount-on-hide="false"
          class="md:fixed top-[62px] md:w-[19.5%] w-full flex flex-col gap-3"
        >
          <template #content>
            <div class="flex flex-col h-40 overflow-y-auto border-x-[#009688] border-b-[#009688] border-1">
                <UInput
                    v-model="selectedPosition"
                    placeholder="Search"
                    color="neutral"
                    variant="ghost"
                    :ui="{
                        trailingIcon: 'text-gray-500 ml-2 dark:text-gray-400',
                        leadingIcon: '',
                        base:'w-full bg-white border-0 border-1  border-[#009688]  h-7 m-2 focus:bg-white focus:outline-[0px] text-base dark:placeholder:text-secondary-4 dark:text-secondary-lite placeholder:text-xs ',
                        root: 'border-0  self-center w-full bg-white',
                    }"
                    class=""
                    @focus="true"
                    @update:model-value="emit('updateSelectedPosition', selectedPosition)"
                />
                <div v-for="i in 7" :key="i" class=" text-sm font-bold bg-white hover:bg-gray-300 border-b-1 border-gray-300 p-1">
                    {{ "Search Result" }}
                </div>
            </div>
          </template>
        </UCollapsible>
    </div>
    <!-- Sector -->
    <div class="flex flex-col basis-1/4">
        <UButton
          :label="selectedSector ? selectedSector : 'Select Sector'"
          as="div"
          color="neutral"
          variant="subtle"
          size="md"
          :trailing-icon="
            isSectorFilterOpen ? 'i-lucide-chevron-up' : 'i-lucide-chevron-down'
          "
          class="text-xs text-gray-500 dark:text-gray-400 bg-white hover:bg-white hover:ring-1 hover:ring-[#009688] "
          block
          @click="isSectorFilterOpen = !isSectorFilterOpen; emit('updateSelectedSector', selectedSector)"
          :ui="{
            base: ' bg-transparent py-[11px] rounded-[0px]  cursor-pointer',
            trailingIcon: 'text-lg',
          }"
        />
        <UCollapsible
          :open="isSectorFilterOpen"
          :unmount-on-hide="false"
          class="md:fixed top-[62px] md:w-[19.5%] w-full flex flex-col gap-3"
        >
          <template #content>
            <div class="flex flex-col h-40 overflow-y-auto border-x-[#009688] border-b-[#009688] border-1">
                <UInput
                    v-model="selectedSector"
                    placeholder="Search"
                    color="neutral"
                    variant="ghost"
                    :ui="{
                        trailingIcon: 'text-gray-500 ml-2 dark:text-gray-400',
                        leadingIcon: '',
                        base:'w-full bg-white border-0 border-1  border-[#009688]  h-7 m-2 focus:bg-white focus:outline-[0px] text-base dark:placeholder:text-secondary-4 dark:text-secondary-lite placeholder:text-xs ',
                        root: 'border-0  self-center w-full bg-white',
                    }"
                    class=""
                    @focus="true"
                    @update:model-value="emit('updateSelectedSector', selectedSector)"
                />
                <div v-for="i in 7" :key="i" class=" text-sm font-bold bg-white hover:bg-gray-300 border-b-1 border-gray-300 p-1">
                    {{ "Search Result" }}
                </div>
            </div>
          </template>
        </UCollapsible>
    </div>
    <!-- City -->
    <div class="flex flex-col basis-1/4">
        <UButton
          :label="selectedCity ? selectedCity : 'Select City'"
          as="div"
          color="neutral"
          variant="subtle"
          size="md"
          :trailing-icon="
            isCityFilterOpen ? 'i-lucide-chevron-up' : 'i-lucide-chevron-down'
          "
          class="text-xs text-gray-500 dark:text-gray-400 bg-white hover:bg-white hover:ring-1 hover:ring-[#009688] rounded-r-lg "
          block
          @click="isCityFilterOpen = !isCityFilterOpen; emit('updateSelectedCity', selectedCity)"
          :ui="{
            base: ' bg-transparent py-[11px] rounded-[0px]  cursor-pointer',
            trailingIcon: 'text-lg',
          }"
        />
        <UCollapsible
          :open="isCityFilterOpen"
          :unmount-on-hide="false"
          class="md:fixed top-[62px] md:w-[19.5%] w-full flex flex-col gap-3"
        >
          <template #content>
            <div class="flex flex-col h-40 overflow-y-auto border-x-[#009688] border-b-[#009688] border-1">
                <UInput
                    v-model="selectedCity"
                    placeholder="Search"
                    color="neutral"
                    variant="ghost"
                    :ui="{
                        trailingIcon: 'text-gray-500 ml-2 dark:text-gray-400',
                        leadingIcon: '',
                        base:'w-full bg-white border-0 border-1  border-[#009688]  h-7 m-2 focus:bg-white focus:outline-[0px] text-base dark:placeholder:text-secondary-4 dark:text-secondary-lite placeholder:text-xs ',
                        root: 'border-0  self-center w-full bg-white',
                    }"
                    class=""
                    @focus="true"
                    @update:model-value="emit('updateSelectedCity', selectedCity)"
                />
                <div v-for="i in 7" :key="i" class=" text-sm font-bold bg-white hover:bg-gray-300 border-b-1 border-gray-300 p-1">
                    {{ "Search Result" }}
                </div>
            </div>
          </template>
        </UCollapsible>
    </div>
    
    </div>
</template>