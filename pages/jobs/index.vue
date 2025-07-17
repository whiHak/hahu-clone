<script setup lang="ts">
const isOpen = ref(true);
const value = ref([0, 3]);
const isChecked = ref(false);
</script>

<template>
  <div class="sm:container mx-auto md:px-8">
    <!-- Sidebar -->
    <JobsSideBar :isOpen="isOpen" />
  </div>
</template>

