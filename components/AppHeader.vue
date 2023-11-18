<template>
    <nav class="bg-white border-b w-full  md:text-sm md:border-none px-4 "
    :class="{ 'fixed top-0 transition-all duration-300 ease-in-out': isFixed }"
    >
    
      <div class="items-center  max-w-screen-xl mx-auto md:flex ">
        <div class="flex items-center justify-between py-3 md:py-5 md:block">
          <a  class="flex gap-4 text-center">
            <!-- <img
              src="https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1662375671324-image_picker888690444996149863.jpg"
              width="50"
              height="50"
              alt="Float UI logo"
            /> -->
          <span class="mx-2 text-2xl text-center  my-auto font-bold">Antrie</span>

          </a>
          <div class="md:hidden">
            <button class="text-gray-500 hover:text-gray-800" @click="toggleState">
              <template v-if="state">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 20 20" fill="currentColor">
                  <path fill-rule="evenodd" d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z" clip-rule="evenodd" />
                </svg>
              </template>
              <template v-else>
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
                </svg>
              </template>
            </button>
          </div>
        </div>
        <div class="flex-1 pb-3 mt-8 md:block md:pb-0 md:mt-0" :class="{ 'block': state, 'hidden': !state }">
          <ul class="justify-end items-center space-y-6 md:flex md:space-x-6 md:space-y-0">
            <li v-for="(item, idx) in navigation" :key="idx" class="text-gray-700 hover:text-indigo-600">
              <a :href="item.path" class="block">{{ item.title }}</a>
            </li>
            <span class="hidden w-px h-6 bg-gray-300 md:block"></span>
            <div class="space-y-3 items-center gap-x-6 md:flex md:space-y-0">
              <li>
                <a href="javascript:void(0)" class="block py-3 text-center text-gray-700 hover:text-indigo-600 border rounded-lg md:border-none">Log in</a>
              </li>
              <li>
                <a href="javascript:void(0)" class="block py-3 px-4 font-medium text-center text-white bg-indigo-600 hover:bg-indigo-500 active:bg-indigo-700 active:shadow-none rounded-lg shadow md:inline">Sign in</a>
              </li>
            </div>
          </ul>
        </div>
      </div>
    </nav>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  // defineProps({
  //   isFixed:String
  // })
  const state = ref(false);
  const isFixed = ref(false);
  
  const toggleState = () => {
    state.value = !state.value;
  };
  
  const navigation = ref([
    { title: "Facilities", path: "javascript:void(0)" },
    { title: "Offered Courses", path: "javascript:void(0)" },
    { title: "Faculties", path: "javascript:void(0)" },
    { title: "Featured Batches", path: "javascript:void(0)" },
    { title: "Reviews", path: "javascript:void(0)" },
  ]);
  
  // Function to handle the scroll event
  const handleScroll = () => {
    if (window.scrollY > 10) {
      isFixed.value = true;
    } else {
      isFixed.value = false;
    }
  };
  
  onMounted(() => {
    // Add a scroll event listener to detect when the user scrolls
    window.addEventListener('scroll', handleScroll);
  });
  
  // Cleanup the event listener when the component is unmounted
  onBeforeUnmount(() => {
    window.removeEventListener('scroll', handleScroll);
  });
  </script>

  