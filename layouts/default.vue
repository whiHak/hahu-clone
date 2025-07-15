<script setup lang="ts">

</script>
<template>
  <div class="min-h-screen flex flex-col text-[#697280] bg-[#ECEDEF] dark:bg-[#02201D] scroll-smooth ">
    <!-- Header -->
    <Header />
    
    <!-- Main Content -->
    <main class="flex-1">
      <slot />
    </main>

    <!-- Footer -->
    <Footer />
  </div>
</template>
