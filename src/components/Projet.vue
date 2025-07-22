<template>
    <section id="portfolio" class="portfolio-section bg-blue-800 py-16 px-4">
      <div class="container mx-auto">
        <div class="text-center mb-12">
          <h2 class="text-4xl text-white font-bold mb-4">Portfolio Showcase</h2>
          <p class="text-lg text-white font-semibold">
            Discover our latest projects and success stories
          </p>
        </div>
  
        <!-- Boutons de filtre -->
        <div class="flex flex-col md:flex-row items-center mb-8">
          <button
            v-for="category in categories"
            :key="category"
            @click="filterProjects(category)"
            class="filter-button bg-blue-500 hover:bg-blue-950 px-4 py-2 mr-2 mb-2 text-white rounded"
            :class="{ 'bg-blue-950': activeCategory === category }"
          >
            {{ category }}
          </button>
        </div>
  
        <!-- Liste des projets -->
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10">
          <div
            v-for="project in filteredProjects"
            :key="project.id"
            class="group portfolio-item relative hover:shadow-lg shadow-md rounded-lg overflow-hidden"
          >
            <a :href="project.link">
              <img
                class="w-full h-60 object-cover"
                :src="project.image"
                :alt="project.title"
              />
              <div
                class="absolute top-0 left-0 right-0 bottom-0 bg-gradient-to-r from-blue-500 to-blue-950 opacity-0 transition duration-300 ease-in-out group-hover:opacity-70"
              ></div>
              <div
                class="p-4 flex flex-col items-center justify-between relative z-10"
              >
                <h3 class="text-lg font-medium text-txt group-hover:text-gray-dark">
                  {{ project.title }}
                </h3>
                <span class="text-sm font-bold text-blue-950 group-hover:text-blue-500">
                  {{ project.category }}
                </span>
              </div>
            </a>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { ref, computed } from "vue";
  
  // Définition des catégories
  const categories = ref(["All", "Web Design", "App Development", "Branding"]);
  const activeCategory = ref("All");
  
  // Liste des projets
  const projects = ref([
    {
      id: 1,
      title: "Logo IT Holding",
      category: "Web Design",
      image: new URL('@/assets/it.png', import.meta.url).href,
      link: "/project-1",
    },
    {
      id: 2,
      title: "Web site Taktyl Labs",
      category: "App Development",
      image: new URL('@/assets/taktyl.jpeg', import.meta.url).href,
      link: "https://taktylabs.com/",
    },
    {
      id: 3,
      title: "Awesome Project 3",
      category: "Web Design, Branding",
      image: new URL('@/assets/it.png', import.meta.url).href,
      link: "/project-3",
    },
    // {
    //   id: 4,
    //   title: "Awesome Project 4",
    //   category: "Web Design, Branding",
    //   image: new URL('@/assets/taktyl.jpeg', import.meta.url).href,
    //   link: "/project-4",
    // },
    // {
    //   id: 5,
    //   title: "Awesome Project 5",
    //   category: "Web Design, Branding",
    //   image: new URL('@/assets/it.png', import.meta.url).href,
    //   link: "/project-5",
    // },
    // {
    //   id: 6,
    //   title: "Awesome Project 6",
    //   category: "Web Design, Branding",
    //   image: new URL('@/assets/taktyl.jpeg', import.meta.url).href,
    //   link: "/project-6",
    // },
  ]);
  
  // Fonction de filtrage des projets
  const filteredProjects = computed(() => {
    if (activeCategory.value === "All") {
      return projects.value;
    }
    return projects.value.filter((project) =>
      project.category.includes(activeCategory.value)
    );
  });
  
  // Changement de catégorie
  const filterProjects = (category) => {
    activeCategory.value = category;
  };
  </script>
  
  <style scoped>
  .filter-button {
    transition: background-color 0.3s ease-in-out;
  }
  </style>
  