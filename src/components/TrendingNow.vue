<template>
  <!-- Featured Wigs Section -->
  <section class="px-6 max-w-7xl mx-auto">
    <div class="flex justify-between items-end mb-8 border-b border-secondary/10 pb-4">
      <h3 class="text-xl md:text-2xl uppercase tracking-widest text-secondary text-left">Trending Now</h3>
    </div>
    
    <div class="grid grid-cols-2 md:grid-cols-4 gap-6 md:gap-8">
      <div v-for="wig in featuredWigs" :key="wig.name" class="group cursor-pointer text-left">
        <div class="aspect-3/4 bg-secondary/5 rounded-2xl overflow-hidden mb-6 relative transition-all duration-700 hover:scale-[1.03]">
          <!-- Product Image -->
          <img :src="`/featured/${wig.img}`" alt="" class="w-full h-full object-cover">
          <!-- Interactive Hover Overlay -->
          <div class="absolute inset-0 bg-secondary/0 group-hover:bg-secondary/5 transition-colors duration-500"></div>
        </div>
        <div class="space-y-1">
          <h5 class="text-xs uppercase tracking-widest font-bold text-secondary">{{ wig.name }}</h5>
          <p class="text-[10px] opacity-60 uppercase tracking-widest">{{ wig.category }}</p>
          <p class="text-sm text-secondary pt-2">{{ wig.price }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup>
const featuredWigs = [
  { name: 'Seamless Silk Straight', category: 'Straight', price: '$299.00', img: 'featured-1.png' },
  { name: 'Honey Aura Curls', category: 'Curly', price: '$349.00', img: 'featured-2.png' },
  { name: 'Urban Muse Gray Bob', category: 'Bob', price: '$279.00', img: 'featured-3.png' },
  { name: 'Velvet Wine Waves', category: 'Lace Front', price: '$389.00', img: 'featured-4.png' }
]
</script>
