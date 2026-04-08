<template>
  <section class="max-w-7xl mx-auto px-6 relative">
    <!-- Section Title -->
    <div class="text-center mb-32 space-y-4 sticky top-12 z-0 opacity-20 pointer-events-none">
      <h3 class="text-[clamp(2rem,6vw,5rem)] font-light italic text-secondary leading-tight uppercase tracking-widest">
        Voices of Confidence
      </h3>
    </div>

    <!-- Sticky Stacked Testimonials -->
    <div class="relative">
      <div v-for="(review, index) in reviews" :key="index"
        class="sticky top-48 flex flex-col md:flex-row items-center gap-12 md:gap-24 p-8 md:p-16 bg-primary/98 backdrop-blur rounded-[3rem] border border-secondary/5 min-h-[60vh] md:min-h-[70vh] transition-all duration-700"
        :style="{ zIndex: (index + 1) * 10,  }"
        :class="[index % 2 !== 0 ? 'md:flex-row-reverse' : '', 'mt-48 first:mt-0']">

        <!-- Portrait Container -->
        <div class="w-full md:w-1/2 aspect-3/4 overflow-hidden rounded-4xl bg-secondary/5 relative">
          <img :src="`/models/${review.img}`" alt="" class="w-full h-full object-cover">
          <!-- Floating Label -->
          <div
            class="absolute bottom-6 right-6 bg-secondary text-primary px-4 py-2 rounded-full text-[8px] uppercase tracking-widest font-bold z-10 shadow-lg">
            Verified Choice
          </div>
        </div>

        <!-- Testimonial Content -->
        <div class="w-full md:w-1/2 space-y-8 flex flex-col justify-center">
          <span class="text-6xl md:text-8xl font-serif text-secondary/5 leading-none h-10 select-none">“</span>

          <p class="text-xl md:text-2xl lg:text-3xl text-secondary leading-tight italic font-light">
            {{ review.text }}
          </p>

          <div class="w-12 h-px bg-secondary/30"></div>

          <div class="space-y-1">
            <h5 class="text-xs uppercase tracking-[0.4em] font-bold text-secondary">{{ review.name }}</h5>
            <p class="text-[10px] uppercase tracking-widest">Brand Ambassador & Customer</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup>
const reviews = [
  {
    name: 'AMARA O.',
    img: 'model1.webp',
    text: 'The Crimson Wave is a pure masterpiece. The deep burgundy tones are so rich, and the body-wave texture is simply breathtaking. I feel like a modern muse every time I wear it.'
  },
  {
    name: 'ZAINAB A.',
    img: 'model2.webp',
    text: 'The Midnight Classic is my daily essential. The lace is truly invisible, and the hair flows so naturally that people assume it’s my own. Total confidence in a box.'
  },
  {
    name: 'NAOMI W.',
    img: 'model3.webp',
    text: 'The Honey Muse transition is absolute perfection. Finding a blonde style that looks this natural on my skin tone has been a dream come true. Truly elite quality.'
  }
]
</script>
