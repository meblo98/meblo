<template>
    <div class="bg-white p-4">
      <!-- Titre changé pour "Experience" -->
      <h2 class="text-3xl md:text-5xl font-bold leading-tight mb-4 pl-10 text-blue-950">Experience</h2>
      
      <div class="flex flex-col grid-cols-9 p-2 mx-auto md:grid">
        <!-- Boucle sur les expériences -->
        <div 
          v-for="(experience, index) in experiences" 
          :key="index" 
          class="flex md:contents" 
          :class="{'flex-row-reverse': index % 2 === 0}"
        >
          <!-- Carte d'expérience -->
          <div 
            class="relative p-4 my-6 text-white bg-blue-800 rounded-xl"
            :class="index % 2 === 0 ? 'col-start-1 col-end-5 mr-auto md:mr-0 md:ml-auto' : 'col-start-6 col-end-10 mr-auto'"
          >
            <h3 class="text-lg font-semibold lg:text-xl">{{ experience.title }}</h3>
            <p class="mt-2 leading-6">{{ experience.description }}</p>
            <span class="absolute text-sm text-blue-950/75 -top-5 left-2 whitespace-nowrap">
              {{ experience.date }}
            </span>
          </div>
  
          <!-- Ligne de timeline avec point -->
          <div class="relative col-start-5 col-end-6 mr-7 md:mx-auto">
            <div class="flex items-center justify-center w-6 h-full">
              <div 
                class="w-1 h-full bg-blue-300"
                :class="{'rounded-t-full bg-gradient-to-b from-blue-400 to-blue-300': index === 0}"
              ></div>
            </div>
            <div class="absolute w-6 h-6 -mt-3 bg-white border-4 border-blue-400 rounded-full top-1/2"></div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  const experiences = [
    {
      title: "web Developer at Taktyl Labs",
      description: "Developed responsive web applications using Vue.js and implemented state management with Pinia and Collaborated on multiple client projects, focusing on UI implementation and API integrations.",
      date: "Feb 2025 - Present"
    },
    {
      title: "Junior Web Developer at Defarsci",
      description: "Collaborated on multiple client projects, focusing on UI implementation and API integrations.",
      date: "Sep 2023 - Dec 2023"
    },
    // {
    //   title: "Intern at DigitalAgency",
    //   description: "Learned modern web development practices and contributed to small-scale projects.",
    //   date: "Mar 2019 - May 2020"
    // },
    {
      title: "Freelance Web Projects",
      description: "Built websites for local businesses while completing my degree.",
      date: "2023 - 2014"
    }
  ];
  </script>
  
  <style scoped>
  /* Styles spécifiques au composant si nécessaire */
  </style>