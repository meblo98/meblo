<template>
    <div class="max-w-screen-xl mx-auto my-7 lg:px-20" id="contact">
      <form @submit.prevent="sendMessage">
        <div class="w-full p-8 my-4 mr-auto shadow-2xl md:px-12 lg:w-9/12 lg:pl-20 lg:pr-40 rounded-2xl">
          <div class="flex">
            <h1 class="text-5xl text-[#0a115c] font-bold">Hire Me</h1>
          </div>
          <div class="grid grid-cols-1 gap-5 mt-5 md:grid-cols-2">
            <input v-model="form.firstName" class="w-full p-3 mt-2 text-gray-900 bg-gray-100 rounded-lg focus:outline-none focus:border-outline" type="text" placeholder="First Name" autocomplete="name" />
            <input v-model="form.lastName" class="w-full p-3 mt-2 text-gray-900 bg-gray-100 rounded-lg focus:outline-none focus:shadow-outline" type="text" placeholder="Last Name" autocomplete="family-name" />
            <input v-model="form.email" class="w-full p-3 mt-2 text-gray-900 bg-gray-100 rounded-lg focus:outline-none focus:shadow-outline" type="email" placeholder="Email" autocomplete="email" />
            <input v-model="form.phone" class="w-full p-3 mt-2 text-gray-900 bg-gray-100 rounded-lg focus:outline-none focus:shadow-outline" type="tel" placeholder="Phone" autocomplete="tel" />
          </div>
          <div class="my-4">
            <textarea v-model="form.message" placeholder="Message" class="w-full h-32 p-3 mt-2 text-gray-900 bg-gray-100 rounded-lg focus:outline-none focus:shadow-outline"></textarea>
          </div>
          <div class="w-1/2 my-2 lg:w-1/4">
            <button type="submit" class="w-full p-3 text-sm font-bold tracking-wide text-gray-100 uppercase bg-[#0a115c] rounded-xl hover:bg-blue-700 focus:outline-none focus:shadow-outline">Send Message</button>
          </div>
        </div>
      </form>
      <div class="w-full px-8 py-12 ml-auto bg-[#5681ff] lg:-mt-96 lg:w-2/6 rounded-2xl">
        <div class="flex flex-col text-white">
          <div class="flex w-2/3 my-4 lg:w-1/2">
            <img class="pt-2 pr-2 h-7 w-7" src="https://img.icons8.com/ios-filled/50/ffffff/marker.png" alt="location" />
            <div>
              <h2 class="text-2xl">Office</h2>
              <p class="text-gray-200">Unité 24, Parcelles Assainies</p>
            </div>
          </div>
          <div class="flex w-2/3 my-4 lg:w-1/2">
            <img class="pt-2 pr-2 h-7 w-7" src="https://img.icons8.com/ios-filled/50/ffffff/phone.png" alt="call us" />
            <div>
              <h2 class="text-2xl">Call</h2>
              <p class="text-gray-200">Tel:+221-77-316-20-01 / +221707977724</p>
            </div>
          </div>
          <div class="flex w-2/3 my-4 lg:w-1/2">
            <img class="pt-2 pr-2 h-7 w-7" src="https://img.icons8.com/ios-filled/50/ffffff/email.png" alt="Email us" />
            <div>
              <h2 class="text-2xl">Email</h2>
              <p class="text-gray-200">lomouhamedelbachir@gmail.com</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { reactive } from 'vue';
  
  const form = reactive({
    firstName: '',
    lastName: '',
    email: '',
    phone: '',
    message: ''
  });
  
  const sendMessage = () => {
    console.log('Form Submitted:', form);
  };
  </script>
  