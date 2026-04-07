<template>
  <div class="fixed top-4 left-4 right-4 z-50 pointer-events-none">
    <nav
      class="pointer-events-auto overflow-hidden bg-primary/20 backdrop-blur-md pr-4 md:px-10 flex justify-between items-center mx-auto max-w-7xl shadow-xl rounded-xl w-full border border-white/10">
      <div class="">
        <img src="/logo.png" alt="Logo" class="w-16 h-16 md:w-20 md:h-20 object-contain">
      </div>
      <ul class="flex gap-6 font-medium text-secondary/90">
        <li class="cursor-pointer hover:text-white transition-colors uppercase tracking-wide text-sm">Home</li>
        <li class="cursor-pointer hover:text-white transition-colors uppercase tracking-wide text-sm">Wigs</li>
        <li class="cursor-pointer hover:text-white transition-colors uppercase tracking-wide text-sm">Contact</li>
      </ul>
    </nav>
  </div>
</template>

<script lang="ts" setup>
</script>

<style scoped></style>