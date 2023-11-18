<template>
  <section class="py-14 w-full px-4 bg-[#000422]">
    <div class="max-w-screen-xl  px-2  md:px-8">
      <div class="text-white">
        <h3 class=" text-3xl font-bold sm:text-4xl">
          Aintrie
        </h3>
        <p class="text-3xl font-bold sm:text-4xl mt-3">
            Provides you with the Best Facilities
        </p>
      </div>
      <div class="mt-12 mx-auto">
        <ul class="grid gap-4 sm:grid-cols-1 md:grid-cols-2 ">
          <li
            v-for="(item, idx) in facilityList"
            :key="idx"
            class="p-4 py-8 rounded-xl border border-solid border-gray-300 bg-white "
          >
          <div class="flex">
            <div class="w-24 h-24 mx-4">
              <img
                :src="item.imageURL"
                class="w-full h-full rounded-full"
                alt=""
              />
            </div>
            <div class="mt-2">
              <h4 class="text-gray-700 font-semibold sm:text-lg">
                {{ item.title }}
              </h4>
              <p class="text-gray-600 mt-2">{{ item.description }}</p>
            </div>
          </div>
            
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>
<script setup>
import { ref } from "vue";

const facilityList = ref([
  {
    title: "Problem Solving ",
    description: "Daily hands on problem solving  ",
    imageURL:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1662375671324-image_picker888690444996149863.jpg",
    active: false,
    status: false,
  },
  {
    title: "Industry Expert Mentors ",
    description:
      "Get mentored by industry experts from Amazon, Apple, Google, Microsoft and more.",
    imageURL:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1662375726220-image_picker7758269648113076255.jpg",
    active: false,
    status: false,
  },
  {
    title: "Personality development classes",
    description:
      "Personality development classes on Sunday for all the students",
    imageURL:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1663171433108-image_picker8702121356753421104.jpg",
    active: false,
    status: false,
  },
]);
</script>
