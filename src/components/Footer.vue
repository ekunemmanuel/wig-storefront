<template>
  <footer class="bg-primary/10 text-black pt-10 md:pt-20 pb-10 px-6 relative overflow-hidden">
    <!-- Big Watermark Logo -->
    <div class="absolute top-1/2 left-1/2 hidden -translate-y-1/2 -translate-x-1/2 pointer-events-none opacity-[0.03] select-none rotate-90 md:rotate-0">
      <h2 class="text-[25vw] font-bold uppercase tracking-tighter whitespace-nowrap leading-none">
        HairStrands
      </h2>
    </div>

    <div class="max-w-7xl mx-auto relative z-10">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12 mb-16">

        <!-- Column 1: Brand & Social -->
        <div class="space-y-6">
          <img src="/logo.png" alt="HairStrands" class="w-24 h-24 object-contain">
          <p class="text-sm opacity-60 max-w-xs leading-relaxed uppercase tracking-widest">
            Redefining luxury hair. Premium wigs for the modern masterpiece.
          </p>
          <div class="flex gap-5">
            <!-- Social Icons (Placeholders with hover effect) -->
            <div v-for="i in 4" :key="i"
              class="w-10 h-10 rounded-full border border-white/10 flex items-center justify-center cursor-pointer hover:bg-white hover:text-primary transition-all duration-300">
              <span class="text-xs uppercase font-bold">{{ ['ig', 'tt', 'pn', 'fb'][i - 1] }}</span>
            </div>
          </div>
        </div>

        <!-- Column 2: Collections -->
        <div class="space-y-6">
          <h3 class="text-xs font-bold uppercase tracking-[0.2em] border-b border-white/10 inline-block">Collections
          </h3>
          <ul class="space-y-3">
            <li class="text-sm opacity-60 hover:opacity-100 cursor-pointer transition-opacity w-fit">The Signature Pink
            </li>
            <li class="text-sm opacity-60 hover:opacity-100 cursor-pointer transition-opacity w-fit">Silken Black
              Classic</li>
            <li class="text-sm opacity-60 hover:opacity-100 cursor-pointer transition-opacity w-fit">Ethereal Blonde
            </li>
            <li class="text-sm opacity-60 hover:opacity-100 cursor-pointer transition-opacity w-fit">Midnight Copper
            </li>
          </ul>
        </div>

        <!-- Column 3: Care & Support -->
        <div class="space-y-6">
          <h3 class="text-xs font-bold uppercase tracking-[0.2em] border-b border-white/10 inline-block">Concierge</h3>
          <ul class="space-y-3">
            <li class="text-sm opacity-60 hover:opacity-100 cursor-pointer transition-opacity w-fit">Shipping &
              Logistics</li>
            <li class="text-sm opacity-60 hover:opacity-100 cursor-pointer transition-opacity w-fit">The Wig Care Guide
            </li>
            <li class="text-sm opacity-60 hover:opacity-100 cursor-pointer transition-opacity w-fit">Returns & Exchanges
            </li>
            <li class="text-sm opacity-60 hover:opacity-100 cursor-pointer transition-opacity w-fit">Private
              Consultation</li>
          </ul>
        </div>

        <!-- Column 4: Newsletter -->
        <div class="space-y-6">
          <h3 class="text-xs font-bold uppercase tracking-[0.2em] border-b border-white/10 inline-block">Inner Circle
          </h3>
          <div class="">
            <p class="text-sm opacity-60 mb-4 leading-relaxed">Join the circle for exclusive drops and styling
              masterclasses.</p>
            <div class="flex flex-col gap-3">
              <input type="email" placeholder="YOUR EMAIL" class="lux-input">
              <button class="lux-button">
                Join Now
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- Bottom Bar -->
      <div class="border-t border-black/10 pt-10 flex flex-col md:flex-row justify-between items-center gap-6">
        <div class="text-[10px] uppercase tracking-widest opacity-40">
          © 2026 HairStrands Global. All Rights Reserved.
        </div>
        <div class="flex gap-8 text-[10px] uppercase tracking-widest opacity-40">
          <span class="hover:opacity-100 cursor-pointer transition-opacity">Privacy Policy</span>
          <span class="hover:opacity-100 cursor-pointer transition-opacity">Terms of Luxury</span>
          <span class="hover:opacity-100 cursor-pointer transition-opacity">Accessibility</span>
        </div>
      </div>
    </div>
  </footer>
</template>

<script lang="ts" setup>
// No extra logic needed for this design-focused footer
</script>

<style scoped></style>