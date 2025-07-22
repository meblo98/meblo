<template>
    <div class="w-full h-full bg-gray-900 dark:bg-gray-200">
      <header class="lg:px-16 px-4 flex flex-wrap bg-blue-950 items-center py-4 shadow-lg">
        <div class="flex-1 flex justify-between items-center">
          <img class="sm:w-[10rem] w-[7rem]" src="@/assets/logo_meblo.png" alt="Logo" />
        </div>
        <button @click="toggleMenu" class="cursor-pointer md:hidden block">
          <svg class="fill-current text-gray-200" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20">
            <title>menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"></path>
          </svg>
        </button>
  
        <div :class="['md:flex md:items-center md:w-auto w-full', { hidden: !isMenuOpen }]">
          <nav>
            <ul class="md:flex items-center justify-between text-base text-white dark:text-white pt-4 md:pt-0">
              <li v-for="(item, index) in menuItems" :key="index">
                <a class="md:p-4 py-3 px-0 block" :href="item.link" :class="{'text-blue-200': index === 0}">{{ item.text }}</a>
              </li>
            </ul>
          </nav>
        </div>
      </header>
  
      <div class="h-full w-full mx-auto relative top-12 pb-20 xl:px-16 px-8 flex md:flex-row flex-col gap-4 justify-center items-center pb-10 pt-4">
        <div class="w-full relative">
          <!-- <img class="shadow-2xl shadow-blue-600 animate-spin absolute left-0 right-0 rounded-full lg:max-w-[70%] max-w-[60%] mx-auto" 
            src="@/assets/meblo.png" alt="My Image" /> -->
          <img class="relative z-10 rounded-full lg:max-w-[70%] max-w-[60%] mx-auto outline outline-[.7rem] outline-offset-[.1rem] outline-blue-400/30" 
            src="@/assets/meblo.png" alt="My Image" />
        </div>
        <div class="w-full flex flex-col justify-center gap-4 md:text-left text-center text-white dark:text-gray-800 md:mt-0 sm:mt-8 mt-4">
          <h1 class="md:text-4xl sm:text-3xl text-2xl font-semibold font-serif">Hello, My name is Mouhamed El Bachir LO </h1>
          <h3 class="capitalize text-blue-400">I'm <span class="typing text-green-500 dark:text-green-700">{{ typedText }}</span></h3>
          <p>Experienced full-stack developer with 4+ years of expertise in Laravel, NestJS, Nuxt.js, Next.js, Android, and some Flutter experience.</p>
          <div class="sm:mt-4 mt-2">
            <button class="px-6 py-1 bg-blue-500 text-white rounded-sm">Get In Touch</button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import { ref, onMounted } from 'vue';
  import Typed from 'typed.js';
  
  export default {
    setup() {
      const isMenuOpen = ref(false);
      const typedText = ref('');
      
      const menuItems = [
        { text: 'Home', link: '#' },
        { text: 'About Me', link: '#' },
        { text: 'Skills', link: '#' },
        { text: 'Services', link: '#' },
        { text: 'Education', link: '#' },
        { text: 'Experience', link: '#' },
        { text: 'Projects', link: '#' },
        { text: 'Contact', link: '#' }
      ];
  
      const toggleMenu = () => {
        isMenuOpen.value = !isMenuOpen.value;
      };
  
      onMounted(() => {
        new Typed('.typing', {
          strings: ['', 'FullStack Developer,', 'Frontend Developer,', 'Backend Developer,', 'Mobile Apps Developer.'],
          typeSpeed: 100,
          backSpeed: 60,
          loop: true
        });
      });
  
      return { isMenuOpen, toggleMenu, menuItems, typedText };
    }
  };
  </script>
  