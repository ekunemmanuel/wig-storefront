<template>
  <!-- Interactive Collections Section -->
  <section class="px-6 max-w-7xl mx-auto">
    <div class="flex justify-between items-end mb-8 border-b border-secondary/10 pb-4">
      <h3 class="text-xl md:text-2xl uppercase tracking-widest text-secondary text-left">Collections</h3>
      <span class="text-[10px] uppercase tracking-widest opacity-60 cursor-pointer hover:opacity-100 transition-opacity">View All</span>
    </div>
    
    <!-- Mobile Swipable Carousel / Desktop Grid -->
    <div class="flex md:grid md:grid-cols-5 gap-4 overflow-x-auto no-scrollbar snap-x snap-mandatory p-4 px-0 md:px-4">
      <div v-for="cat in categories" :key="cat.name"
        class="min-w-[240px] md:min-w-0 snap-center group cursor-pointer text-left">
        <div class="aspect-4/5 bg-secondary/5 rounded-2xl overflow-hidden mb-4 relative transition-all duration-700 hover:scale-[1.03]">
          <!-- Collection Portrait -->
          <img :src="`/categories/${cat.img}`" alt="" class="w-full h-full object-cover grayscale-20 group-hover:grayscale-0 transition-all duration-700">
          <div class="absolute inset-0 bg-linear-to-t from-black/40 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
        </div>
        <h4 class="text-xs uppercase tracking-[0.2em] text-center font-bold text-secondary">{{ cat.name }}</h4>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup>
const categories = [
  { name: 'Straight', img: 'straight.png' },
  { name: 'Curly', img: 'curly.png' },
  { name: 'Bob', img: 'bob.png' },
  { name: 'Lace Front', img: 'lace-front.png' },
  { name: 'Colored', img: 'colored.png' }
]
</script>
