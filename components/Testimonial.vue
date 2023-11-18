<template>
  <section class="py-14  lg:hidden" >
    <div class="max-w-screen-xl mx-auto px-4 md:px-8 ">
      <div class="max-w-3xl mx-auto text-center">
        <h3 class="text-gray-400 font-semibold pb-2">
          Our Testimonials
        </h3>
        <div class="text-slate-800 text-3xl my-2 font-bold ">
         What Student's Say ?
        </div>
        <ul>
          <li v-for="(item, idx) in testimonialList" :key="idx">
            <figure v-if="currentTestimonial === idx">
              <div class="mt-6">
                <img
                  :src="item.imgUrl"
                  class="w-24 h-24 mx-auto rounded-full"
                />
                <div class="mt-3">
                  <span class="block text-slate-800 text-xl font-semibold">{{
                    item.name
                  }}</span>
                  <div class="block text-gray-500 my-4">{{
                    item.bio
                  }}</div>
                </div>
              </div>
            
                <p class="text-gray-500 text-xl  ">
                  {{ item.comments }}
                </p>
              
             
            </figure>
          </li>
        </ul>
      </div>
      <div class="mt-6">
        <ul class="flex gap-x-3 justify-center">
          <li v-for="(item, idx) in testimonialList" :key="idx">
            <button
              class="w-2.5 h-2.5 rounded-full duration-150 ring-offset-2"
              :class="[
                currentTestimonial === idx
                  ? 'ring-indigo-600 bg-indigo-600'
                  : 'ring-gray-300 bg-gray-300',
                'focus:ring',
              ]"
              @click="setCurrentTestimonial(idx)"
            ></button>
          </li>
        </ul>
      </div>
    </div>
  </section>
  <section class="py-14 hidden lg:block ">
    <div class="max-w-screen-xl mx-auto px-4 text-center md:px-8 ">
      <div class="max-w-xl mx-auto">
        <h3 class="text-gray-400 font-semibold pb-2">
          Our Testimonials
        </h3>
        <div class="text-slate-800 text-3xl my-2 font-bold ">
         What Student's Say ?
        </div>
      </div>
      <div class="mt-12">
        <ul class="grid gap-8 sm:grid-cols-2 md:grid-cols-3">
          <li v-for="(item, idx) in testimonialList" :key="idx">
            <div class="w-28 h-28 mx-auto">
              <img :src="item.imgUrl" class="w-full h-full rounded-full" alt="">
            </div>
            <div class="mt-2">
              <h4 class="text-gray-700 font-semibold sm:text-lg">{{ item.name }}</h4>
              <p class="text-indigo-600">{{ item.bio }}</p>
              <p class="text-gray-600 mt-2">{{ item.comments }}</p>
              
            </div>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>
<script setup>
import { ref } from "vue";
const currentTestimonial = ref(0);
const setCurrentTestimonial = (index) => {
  currentTestimonial.value = index;
};
const testimonialList = ref([
  {
    name: "Aanya ",
    bio: "CSE, IIT Bombay",
    // imgUrl:
    //   "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1663169571889-image_picker2996683955809270566.jpg",
    comments:
      "The trainers are industry experts. I have learnt Java, DSA and Android.",
    active: true,
  },
  {
    name: "Nikhil Kumar",
    bio: "2nd Year, B.N College",
    // imgUrl:
    //   "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1663169922796-image_picker170968792975919416.jpg",
    comments: "Best Coding classes in Patna. Rishi sir is one of the best.",
    active: true,
  },
  {
    name: "Harsh Raj",
    bio: "Data Analyst at Bank of America",
    // imgUrl:
    //   "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1663169328262-image_picker5373033690363063736.jpg",
    comments:
      "A lot of thanks to Coding Age and their industry expert faculties who trained me in Python and Data Science and helped me get a Job at Bank of America as a data analyst.",
    active: true,
  },
]);


</script>
