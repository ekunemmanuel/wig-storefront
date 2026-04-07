<template>
  <div class="h-screen flex flex-col p-4 pt-24 md:pt-28 gap-4 relative">
    <div class="flex flex-col lg:flex-row gap-4 flex-1 min-h-0">
      <div class="flex flex-col flex-1 min-h-0">
        <!-- Main Image Section (Mobile Carousel / Desktop Grid) -->
        <!-- Main Image Section (Mobile Carousel / Desktop Grid) -->
        <div class="relative flex-1 min-h-0 mb-4 group">
          <div ref="carouselRef" @scroll="handleScroll"
            class="flex lg:grid lg:grid-cols-3 gap-4 h-full items-stretch overflow-x-auto snap-x snap-mandatory no-scrollbar">

            <!-- Unified List for Images (Looping on Mobile, Grid on Desktop) -->
            <div v-for="(img, i) in displayImages" :key="i"
              class="min-w-full lg:min-w-0 flex-1 h-full snap-center rounded-2xl overflow-hidden aspect-3/4 md:aspect-auto"
              :class="{ 'lg:hidden': i === 0 || i === displayImages.length - 1 }">
              <img :src="`/${img}`" alt="Wig Style" class="w-full h-full object-cover" loading="eager" width="800"
                height="1200">
            </div>
          </div>

          <!-- Carousel Indicators (Mobile Only) -->
          <div
            class="lg:hidden absolute bottom-4 left-1/2 -translate-x-1/2 flex gap-2.5 z-10 bg-black/20 backdrop-blur-md px-4 py-2 rounded-full border border-white/10">
            <div v-for="(_, i) in allMobileImages" :key="i" class="w-2 h-2 rounded-full transition-all duration-300"
              :class="activeIndex === i ? 'bg-white scale-125 shadow-[0_0_8px_rgba(255,255,255,0.8)]' : 'bg-white/30'">
            </div>
          </div>
        </div>

        <!-- Branding Text (Always at bottom) -->
        <div class="py-4 mt-auto">
          <h1 class="text-[clamp(3.2rem,8vw,15rem)] font-bold">
            HairStrands
          </h1>
          <p class="text-[clamp(1.5rem,8vw,7rem)] w-full opacity-80">
            Premium Wigs for Every Style
          </p>
        </div>
      </div>

      <!-- Desktop Hero Image (Hidden on mobile as it's correctly placed in the carousel) -->
      <div class="hidden lg:block w-full h-full rounded-2xl overflow-hidden">
        <img src="/hero.png" alt="" class="w-full h-full object-cover" fetchpriority="high" loading="eager" width="1200"
          height="1600">
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref, onMounted, onUnmounted, computed } from 'vue'

// Base Images
const modelImages = ['wig4.png', 'wig5.png', 'wig6.png', 'wig7.png', 'wig8.png', 'wig9.png',]
const allMobileImages = ['hero.png', ...modelImages]

// Infinite Looping logic:
// We append a clone of the first image to the end to permit smooth forward looping.
const displayImages = [...allMobileImages, allMobileImages[0]]

// Carousel State
const carouselRef = ref<HTMLElement | null>(null)
const activeIndex = ref(0)
let autoPlayInterval: any = null

// Update indicators during manual swipe
const handleScroll = (e: Event) => {
  const container = e.target as HTMLElement
  if (!container) return
  const scrollIndex = Math.round(container.scrollLeft / container.clientWidth)
  // Maps the cloned index back to the first indicator dot
  activeIndex.value = scrollIndex % allMobileImages.length
}

const startAutoPlay = () => {
  if (autoPlayInterval) clearInterval(autoPlayInterval)

  autoPlayInterval = setInterval(() => {
    if (!carouselRef.value || window.innerWidth >= 1024) return
    const container = carouselRef.value

    // Smoothly scroll to the next slide in our 'displayImages' array
    const nextScrollIndex = (Math.round(container.scrollLeft / container.clientWidth) + 1)

    container.scrollTo({
      left: nextScrollIndex * container.clientWidth,
      behavior: 'smooth'
    })

    // If we just scrolled to the CLONE (the last item in displayImages)
    if (nextScrollIndex === displayImages.length - 1) {
      // Small pause to allow smooth scroll to finish, then SILENTLY jump back to index 0
      setTimeout(() => {
        if (container) {
          container.scrollTo({ left: 0, behavior: 'auto' })
          activeIndex.value = 0
        }
      }, 700)
    } else {
      activeIndex.value = nextScrollIndex % allMobileImages.length
    }
  }, 2000)
}

const stopAutoPlay = () => {
  if (autoPlayInterval) clearInterval(autoPlayInterval)
}

onMounted(() => {
  setTimeout(startAutoPlay, 1000)
})

onUnmounted(stopAutoPlay)
</script>

<style></style>