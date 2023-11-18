<template>
   
  <section class="py-14 w-full  ">
    <div class="  px-2  md:px-8">
      <div class="text-center ">
        <div class=" text-2xl text-slate-500">
          Offered Courses at Aintrie

        </div>
        <div class="text-3xl font-bold sm:text-4xl mt-3">
           Browse Our Top Courses
        </div>
      </div>
      <div class="mt-12 mx-auto">
        <ul class="grid gap-4  sm:grid-cols-1 lg:grid-cols-3 md:grid-cols-3 ">
          <li
            v-for="(item, idx) in courseList"
            :key="idx"
            class="  rounded-lg border border-solid border-gray-300 bg-white "
          >
          <div class="flex">
            <div class="w-1/2 h-full my-auto">
              <img
              v-if="item.imageUrl"
                :src="item.imageUrl"
                class="w-full "
                alt=""
              />
              <img
             v-else
              src="https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1668284831271-"
                class="w-full  my-auto "
                alt=""
              />

            </div>
            <div class=" w-1/2 p-2 my-auto">
              <h4 class="text-slate-700 font-semibold sm:text-lg">
                {{ item.name }}
              </h4>
              <p class="text-slate-500 text-sm my-2 ">{{ item.description }}</p>
              <div class="bg-[rgba(94,86,105,.06)] text-indigo-500 p-2 rounded my-4 ">
               Duration: {{ item.duration }}
              </div>
            </div>
          </div>
            
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const courseList = ref([
  {
    name: "Single language B",
    description: "Java",
    prerequisites: "None",
    duration: "3 months",
    courseFee: 9000,
    active: true,
    imageUrl:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1668494459465-",
  },
  {
    name: "Junior coding",
    description: "For school students",
    prerequisites: "None",
    duration: "8 months",
    courseFee: 12000,
    active: true,
    imageUrl:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1668494480733-",
  },
  {
    name: "C/C++ Programming",
    description: "Introduction to programming using C/C++",
    prerequisites: "None",
    duration: "2 months",
    courseFee: 6000,
    active: true,
    imageUrl:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1668494498208-",
  },
  {
    name: "Full Stack Development",
    description:
      "Backend development with Java, Spring boot, MySQL, mongodb. Front end development with Html, CSS, JavaScript and VueJs. Regular tests, mock interviews and placement assistance.",
    prerequisites: "None",
    duration: "9 months",
    courseFee: 35000,
    active: true,
    imageUrl:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1668284831271-",
  },
  {
    name: "DSA",
    description:
      "Learn problem solving with Java &  DSA. During the course, you will be solving the questions asked in top tech companies. Test after completion of every data structure. Mock interviews. Placement Assistance.",
    prerequisites: "Understanding of programming language",
    duration: "6 months",
    courseFee: 25000,
    active: true,
    imageUrl:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1668494551207-",
  },
  {
    name: "Introduction to Programming with C/C++/Java/Python",
    description: "Introduction to Programming",
    prerequisites: "None",
    duration: "6 months",
    courseFee: 18000,
    active: true,
    imageUrl: null,
  },
  {
    name: "Single language A",
    description: "C/ C++ or python",
    prerequisites: "No",
    duration: "2 months",
    courseFee: 6000,
    active: true,
    imageUrl: null,
  },
]);
// const isScrollable = ref(false);
// const showRightIndicator = ref(false);
// const checkScrollable = () => {
//   const container = document.getElementById('event-container');
//   isScrollable.value = container.scrollWidth > container.clientWidth;
//   showRightIndicator.value = container.scrollLeft < container.scrollWidth - container.clientWidth;
// };

// const scrollLeft = () => {
//   const container = document.getElementById('event-container');
//   container.scrollBy({ left: -200, behavior: 'smooth' });
// };

// const scrollRight = () => {
//   const container = document.getElementById('event-container');
//   container.scrollBy({ left: 200, behavior: 'smooth' });
// };

// onMounted(() => {
//   checkScrollable();
//   window.addEventListener('resize', checkScrollable);
// });

// onUnmounted(() => {
//   window.removeEventListener('resize', checkScrollable);
// });
</script>
<style scoped>
#event-container {
  position: relative;
  /* background-color: #000; */
  padding: 8px;
  overflow-x: scroll;
  scrollbar-width: thin;
  scrollbar-color: #888 #f1f1f1;
}

#event-container::-webkit-scrollbar {
  height: 8px;
}

#event-container::-webkit-scrollbar-track {
  background-color: #f1f1f1;
}

#event-container::-webkit-scrollbar-thumb {
  background-color: #888;
  border-radius: 4px;
}

#event-container::-webkit-scrollbar-thumb:hover {
  background-color: #555;
}

/* Scroll Indicator Styles */
.scroll-indicator {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 40px;
  height: 40px;
  background-color: rgb(24, 23, 23); /* Set the desired background color */
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 30;
  /* transition: opacity 0.3s; */
}

.scroll-indicator.left {
  left: 0;
  /* transform: translate(-50%, -50%); */
}

.scroll-indicator.right {
  right: 0;
  /* transform: translate(-50%, -50%); */
}

.scroll-indicator.hidden {
  opacity: 0;
}

.scroll-icon {
  width: 10px;
  height: 10px;
  border-top: 3px solid #efe8e8;
  border-right: 3px solid #f5f2f2;
  transform: rotate(45deg);
  font-weight: bolder;
}
.scroll-iconleft {
  width: 10px;
  height: 10px;
  border-top: 3px solid #f7f2f2;
  border-right: 3px solid #fbf3f3;

  transform: rotate(225deg);
  font-weight: bolder;
}
</style>