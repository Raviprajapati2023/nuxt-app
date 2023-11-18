<template>
    <section class="py-14">
      <div class="max-w-screen-xl mx-auto px-2 text-center md:px-8">
        <div class="">
          <h3 class="text-gray-800 text-3xl w-full w-full font-semibold sm:text-4xl text-center">
            With Great Outcomes.
          </h3>
          <div class="text-gray-600 w-full w-full text-center text-lg my-6 mb-8">
            Our students have gotten offers from awesome companies.
          </div>
          <div class="image-slider">
            <div class="slider-container" :style="sliderStyle">
              <div class="image-slide" v-for="(company, index) in companies" :key="company.name + index">
                <img :src="company.img" :alt="company.name" class="w-36" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
 const companies = [
    {
      name: 'a',
      img: 'https://seeklogo.com/images/G/google-2015-new-logo-FFFC46553B-seeklogo.com.png',
    },
    {
      name: 'b',
      img: 'https://seeklogo.com/images/A/amazon-logo-E45AFA9F25-seeklogo.com.png',
    },
    {
      name: 'c',
      img: 'https://seeklogo.com/images/F/flipkart-logo-5CE68C24AF-seeklogo.com.png',
    },
    {
      name: 'd',
      img: 'https://seeklogo.com/images/S/Simon-logo-D93DFD1518-seeklogo.com.png',
    },
    {
      name: 'e',
      img: 'https://seeklogo.com/images/S/simon-data-logo-5D0A739045-seeklogo.com.png',
    },
    {
      name: 'h',
      img: 'https://seeklogo.com/images/M/microsoft-logo-B5C9E49146-seeklogo.com.png',
    },
    {
      name: 'i',
      img: 'https://seeklogo.com/images/U/uber-eats-logo-D146CA8D8B-seeklogo.com.png',
    },
    {
      name: 'j',
      img: 'https://seeklogo.com/images/C/cornershop-logo-6B4F8F961F-seeklogo.com.png',
    },
    {
      name: 'k',
      img: 'https://seeklogo.com/images/O/oyo-rooms-logo-ADDE1C74DB-seeklogo.com.png',
    },
  ];
  
  let currentIndex = 0;
  const totalCompanies = companies.length;
  
  const sliderStyle = computed(() => ({
    transform: `translateX(-${currentIndex * 100}%)`,
  }));
  
  // Auto-slide every 3 seconds
  setInterval(() => {
    currentIndex = (currentIndex + 1) % totalCompanies;
  }, 3000);
  </script>
  
  <style scoped>
  .image-slider {
    overflow: hidden;
    position: relative;
  }
  
  .slider-container {
    display: flex;
    white-space: nowrap;
    width: max-content;
    animation: slide 10s linear infinite;
  }
  
  .image-slide {
    min-width: 14rem;
    display: inline-block;
  }
  
  @keyframes slide {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-100%);
    }
  }
  </style>
  