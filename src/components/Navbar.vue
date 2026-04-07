<template>
  <div class="fixed top-4 left-4 right-4 z-50 pointer-events-none">
    <nav
      class="pointer-events-auto overflow-hidden bg-primary/20 backdrop-blur-md pr-4 md:px-10 flex justify-between items-center mx-auto max-w-7xl shadow-xl rounded-xl w-full border border-white/10 min-h-[64px] md:min-h-[80px]">
      <div class="flex items-center">
        <img src="/logo.png" alt="Logo" class="w-16 h-16 md:w-20 md:h-20 object-contain" width="80" height="80"
          fetchpriority="high" loading="eager">
      </div>
      <ul class="flex gap-6 font-medium text-secondary/90 items-center h-full">
        <li class="cursor-pointer hover:text-black transition-colors uppercase tracking-wide text-sm leading-none">Home
        </li>
        <li class="cursor-pointer hover:text-black transition-colors uppercase tracking-wide text-sm leading-none">Wigs
        </li>
        <li class="cursor-pointer hover:text-black transition-colors uppercase tracking-wide text-sm leading-none">
          Contact</li>
      </ul>
    </nav>
  </div>
</template>

<script lang="ts" setup>
</script>

<style scoped></style>