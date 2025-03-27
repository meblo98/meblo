<template>
    <div class="w-screen h-full m-auto p-3 bg-blue-900 bg-no-repeat bg-cover" :style="backgroundStyle">
      <div class="xl:w-[70%] lg:w-[80%] md:w-[90%] m-auto md:px-0 px-4 md:my-10 bg-[#111111] dark:bg-white rounded-xl overflow-hidden">
        <!-- What I DO -->
        <section class="w-full h-full flex flex-col justify-center md:py-20 py-10 md:px-20 px-2">
          <!-- Heading -->
          <div class="w-fit">
            <h2 class="text-2xl font-bold text-white dark:text-blue-950 pb-2">{{ sectionTitle }}</h2>
            <div class="rounded-t-full border-[1px] border-blue-500 dark:border-blue-400 overflow-hidden">
              <hr class="border-[3px] border-blue-700 dark:border-blue-700 w-[20%]" />
            </div>
          </div>
  
          <div class="w-full grid md:grid-cols-2 grid-cols-1 gap-4 mt-8">
            <!-- Services Items -->
            <div 
              v-for="(service, index) in services" 
              :key="index" 
              class="flex sm:gap-4 gap-1"
            >
              <span>
                <ion-icon 
                  :name="service.icon" 
                  class="sm:text-5xl text-3xl text-blue-400 dark:text-blue-600"
                ></ion-icon>
              </span>
  
              <div class="flex flex-col gap-2">
                <h3 class="text-xl font-semibold text-white dark:text-blue-950">{{ service.title }}</h3>
                <p class="text-gray-400 dark:text-gray-600">
                  {{ service.description }}
                </p>
              </div>
            </div>
          </div>
        </section>
      </div>
    </div>
  </template>
  
  <script setup>
  import { computed } from 'vue';
  
  // Données réactives
  const backgroundImageUrl = 'https://images.unsplash.com/photo-1620121692029-d088224ddc74?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w0NzEyNjZ8MHwxfHNlYXJjaHwxNXx8Z3JhcGhpY3MlMjBiYWNrZ3JvdW5kfGVufDB8MHx8fDE3MzUyODE0NTB8MA&ixlib=rb-4.0.3&q=80&w=1080';
  const sectionTitle = 'What I Do';
  
  const services = [
    {
      icon: 'code-slash-outline',
      title: 'Web Development',
      description: 'Crafting responsive and intuitive websites tailored to your unique needs using cutting-edge technologies.'
    },
    {
      icon: 'browsers-outline',
      title: 'UI/UX Design',
      description: 'Creating visually appealing and user-centric designs that enhance user experiences and engagement.'
    },
    {
      icon: 'archive-outline',
      title: 'Custom CMS Solutions',
      description: 'Building reusable and efficient CMS APIs to simplify website management and scalability.'
    },
    {
      icon: 'phone-portrait-outline',
      title: 'Mobile App Dev\'t',
      description: 'Designing and developing user-friendly mobile applications for iOS and Android, ensuring seamless performance and user satisfaction.'
    },
    {
      icon: 'bag-check-outline',
      title: 'E-commerce Development',
      description: 'Creating robust platforms to elevate your online business presence.'
    },
    {
      icon: 'swap-horizontal-outline',
      title: 'API Integration',
      description: 'Seamlessly connecting systems to enhance functionality and performance.'
    }
  ];
  
  // Style calculé pour l'arrière-plan
  const backgroundStyle = computed(() => ({
    backgroundImage: `url(${backgroundImageUrl})`
  }));
  </script>
  
  <style scoped>
  /* Styles spécifiques au composant */
  </style>