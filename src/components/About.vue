<template>
  <section class="min-h-screen bg-blue-800 text-blue-200 py-16 px-6 flex flex-col md:flex-row items-center justify-between gap-8">
    <!-- Left Side: Image -->
    <div class="w-full md:w-5/12 flex justify-center h-full md:justify-end">
      <img 
        :src="imageUrl" 
        :alt="imageAlt" 
        class="w-72 h-96 md:w-80 lg:w-96 object-cover rounded-lg shadow-lg" 
      />
    </div>

    <!-- Right Side: Text Content -->
    <div class="w-full md:w-7/12 text-center md:text-left relative">
      <!-- Vertical Text -->
      <div class="absolute left-[40%] -top-6 md:-left-16 lg:top-0 md:top-6 rotate-0 md:rotate-[-90deg] text-sm tracking-widest">
        <div class="flex items-center justify-center gap-2">
          <div class="w-16 h-[2px] bg-blue-200"></div>
          <p>{{ verticalText }}</p>
        </div>
      </div>

      <!-- Main Heading -->
      <h2 class="text-3xl md:text-5xl font-bold leading-tight mb-4 pl-10">
        {{ titleLine1 }} <br> {{ titleLine2 }}
      </h2>

      <!-- Description -->
      <p class="text-blue-200 mb-6 text-sm md:text-base leading-relaxed max-w-2xl mx-auto md:mx-0">
        {{ description }}
      </p>

      <!-- Buttons -->
      <div class="flex flex-col sm:flex-row gap-4 justify-center md:justify-start">
        <a 
          href="#" 
          class="bg-blue-200 text-blue-950 font-semibold py-2 px-4 rounded-lg hover:bg-blue-500/80 text-center transition-colors duration-300"
        >
          {{ primaryButtonText }}
        </a>
        <a 
          href="#" 
          class="border border-blue-950 text-blue-950 font-semibold py-2 px-4 rounded-lg hover:bg-blue-950/10 text-center transition-colors duration-300"
        >
          {{ secondaryButtonText }}
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
// Données réactives
const imageUrl = '@/assets/meblo.jpg';
const imageAlt = 'About Me';
const verticalText = 'MORE ABOUT';
const titleLine1 = 'A Passionate';
const titleLine2 = 'Software Developer';
const description = "I'm Mouhamed El Bachir LO, a passionate Software Developer with expertise in Vue.js, Laravel, & modern web technologies. I specialize in building user-friendly applications that solve real-world problems. With a deep understanding of frontend development, state management, and API integration, I can bring your ideas to life.";
const primaryButtonText = 'See Projects';
const secondaryButtonText = 'More Details';
</script>

<style scoped>
/* Styles spécifiques au composant si nécessaire */
</style>