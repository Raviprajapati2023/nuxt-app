<template>
    <div class="bg-white py-8 ">
      <div class="mx-auto  px-4 lg:px-8">
        <div class="mx-auto max-w-2xl text-center">
          <h2 class="text-3xl font-semibold tracking-tight text-gray-900 sm:text-4xl">Image Gallary</h2>
        </div>
        <div class="mx-auto mt-16 grid auto-rows-fr grid-cols-1 gap-8 sm:mt-20 lg:mx-0 lg:max-w-none lg:grid-cols-3">
          <article v-for="post in galleryList" :key="post.title" class="relative isolate flex flex-col justify-end overflow-hidden rounded-2xl bg-gray-900 px-8 pb-8 pt-80 sm:pt-48 lg:pt-80">
            <img :src="post.imageURL" alt="" class="absolute inset-0 -z-10 h-full w-full object-cover" />
            <div class="absolute inset-0 -z-10 bg-gradient-to-t from-gray-900 via-gray-900/40" />
            <div class="absolute inset-0 -z-10 rounded-2xl ring-1 ring-inset ring-gray-900/10" />
  
            <div class="flex flex-wrap items-center gap-y-1 overflow-hidden text-sm leading-6 text-gray-300">
              <div class="-ml-4 flex items-center gap-x-4">
                <svg viewBox="0 0 2 2" class="-ml-0.5 h-0.5 w-0.5 flex-none fill-white/50">
                  <circle cx="1" cy="1" r="1" />
                </svg>
                <div class="flex gap-x-2.5">
                  {{ post.title }}
                </div>
              </div>
            </div>
            <h3 class="mt-3 text-lg font-semibold leading-6 text-white">
              <a >
                <span class="absolute inset-0" />
                {{ post.description }}
              </a>
            </h3>
          </article>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import {ref} from "vue"

  const galleryList = ref([
  {
    title: "Teacher's day celebration",
    description: "Students celebrating teacher's day at our Kankarbagh Center.",
    imageURL:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1663164320577-image_picker9044707527612968456.jpg",
    status: true,
  },
  {
    title: "CodeUps",
    description: "Biweekly coding meetups on new technologies",
    imageURL:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1675851081475-",
    status: true,
  },
  {
    title: "",
    description: "",
    imageURL:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1679738286364-",
    status: true,
  },
]);

        const facultyList =  ref([
            {
                name: "Rishi ",
                experience: "8+ Years Industry Experience ",
                photoUrl: "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1662375798468-image_picker6393028551827813776.jpg",
                description: "Bit Mesra Alumni. Ex. Lead Software Engineer. Developed and scaled products for millions of users.",
                active: true
            },
            {
                name: "Abhishek",
                experience: "3 Months",
                photoUrl: "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1663164594692-image_picker7738084370600353889.jpg",
                description: "Seasoned Personality Development , public speaking trainer. Have trained many professionals working in icrosoft Google and many top MNCs.",
                active: true
            }
        ])
  </script>