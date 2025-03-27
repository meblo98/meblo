<template>
    <section>
      <div class="bg-white dark:bg-white-800 transition-colors duration-500">
        <div class="w-full mx-auto 2xl:max-w-7xl items-center flex flex-col lg:h-svh justify-center py-24 lg:py-20 relative p-8">
          <!-- Titre "Education" ajouté -->
          <div class="prose text-gray-500 prose-sm prose-headings:font-normal prose-headings:text-xl mx-auto">
            <div>
              <h1  class="text-3xl md:text-5xl font-bold leading-tight mb-4 pl-10 text-blue-950">Education</h1>
              <p class="text-balance">
                My academic background and professional certifications.
              </p>
            </div>
          </div>
  
          <div class="mt-6 border-t pt-12">
            <!-- Timeline Component -->
            <div class="bg-white dark:bg-blue-800 rounded-2xl p-8 border">
              <div class="mx-auto grid grid-cols-1 gap-8 overflow-hidden lg:mx-0 lg:grid-cols-4">
                <!-- Timeline Items -->
                <div v-for="(item, index) in timelineItems" :key="index">
                  <time :datetime="item.date" class="flex items-center text-sm font-semibold leading-6 text-orange-600 dark:text-orange-400">
                    <svg viewBox="0 0 4 4" class="mr-4 h-1 w-1 flex-none" aria-hidden="true">
                      <circle cx="2" cy="2" r="2" fill="currentColor"></circle>
                    </svg>
                    {{ item.date }}
                    <div class="absolute -ml-2 h-px w-screen -translate-x-full bg-gray-900/10 dark:bg-gray-500 sm:-ml-4 lg:static lg:-mr-6 lg:ml-8 lg:w-auto lg:flex-auto lg:translate-x-0" aria-hidden="true"></div>
                  </time>
                  <p class="mt-6 text-lg font-semibold leading-8 tracking-tight text-gray-900 dark:text-white">
                    {{ item.title }}
                  </p>
                  <p class="mt-1 text-sm text-pretty leading-7 text-gray-500 dark:text-gray-300">
                    {{ item.description }}
                  </p>
                </div>
              </div>
            </div>
  
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  
  const timelineItems = [
    {
      date: "Aug 2021",
      title: "Bachelor's Degree in Computer Science",
      description: "Graduated with honors from Institut Polytechnique des Metier (IPM) with a focus on software development and security."
    },
    {
      date: "Jul 2023",
      title: "Advanced Web Development Certification",
      description: "Completed intensive training in modern web technologies and frameworks from XARALA."
    },
    {
      date: "Nov 2024",
      title: "Advanced Web Development Certification",
      description: "Completed intensive training in modern web technologies and frameworks and Acquired skills in user interface design and user experience principles from SIMPLON Sénégal."
    },
    {
      date: "Jan 2025",
      title: "Cloud Computing Certification",
      description: "Earned professional certification in cloud infrastructure and services."
    }
  ];
  </script>
  
  <style scoped>
  /* Styles spécifiques au composant */
  </style>