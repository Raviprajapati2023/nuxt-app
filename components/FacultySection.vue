<template>
  <section class="py-14 w-full hidden lg:block">
    <div class="px-2 md:px-8">
      <div class="text-center">
        <div class="text-2xl text-slate-500">Aintrie Provides you with the</div>
        <div class="text-3xl font-bold sm:text-4xl mt-3">
          Industry Expert Faculty
        </div>
      </div>
      <div class="mt-12 mx-auto ">
        <ul class="gap-4 flex justify-center ">
          <li
            v-for="(item, idx) in facultyList"
            :key="idx"
            class="p-4 ml-8  rounded-xl border border-solid border-gray-300 w-1/3"
          >
            <div class="w-32 h-32 mx-auto">
              <img
                :src="item.photoUrl"
                class="w-full h-full rounded-full"
                alt=""
              />
            </div>
            <div class="mt-2">
              <h4
                class="text-slate-700 font-semibold sm:text-lg text-center my-4"
              >
                {{ item.name }}
              </h4>
              <p class="text-slate-500 my-2">
                {{ item.description }}
              </p>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </section>
  <section class="py-14 w-full lg:hidden ">
    <div class="px-2 md:px-8 relative">
      <div class="text-center">
        <div class="text-2xl text-slate-500">Aintrie Provides you with the</div>
        <div class="text-3xl font-bold sm:text-4xl mt-3">
          Industry Expert Faculty
        </div>
      </div>
      <div class="mt-12 bg-red-500  mx-auto">
        <ul
          id="event-container"
          class="py-8 gap-6 overflow-x-scroll flex flex-nowrap "
        >
          <li
            v-for="(item, idx) in facultyList"
            :key="idx"
            class="p-2 rounded-xl border border-solid border-gray-300 w-5/6 ml-8 group cursor-pointer  mb-8 md:w-3/4 xl:w-1/3 flex-shrink-0"
          >
            <div class="w-32 h-32 mx-auto">
              <img
                :src="item.photoUrl"
                class="w-full h-full rounded-full"
                alt=""
              />
            </div>
            <div class="mt-2">
              <h4
                class="text-slate-700 font-semibold sm:text-lg text-center my-4"
              >
                {{ item.name }}
              </h4>
              <p class="text-slate-500 my-2">
                {{ item.description }}
              </p>
            </div>
          </li>
        </ul>
      </div>
      <button class="btn btn-prev" @click="scrollLeft">
        <div class="scroll-iconleft"></div>
      </button>
      <button class="btn btn-next cursor-pointer inline" @click="scrollRight">
        <div class="scroll-icon"></div>
      </button>
    </div>
  </section>
</template>
<script setup>
import { ref, onMounted, onUnmounted } from "vue";
const facultyList = ref([
  {
    name: "Rishi ",
    experience: "8+ Years Industry Experience ",
    photoUrl:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1662375798468-image_picker6393028551827813776.jpg",
    description:
      "Bit Mesra Alumni. Ex. Lead Software Engineer. Developed and scaled products for millions of users.",
    active: true,
  },
  {
    name: "Abhishek",
    experience: "3 Months",
    photoUrl:
      "https://s3.ap-south-1.amazonaws.com/sms-bucket-01/1663164594692-image_picker7738084370600353889.jpg",
    description:
      "Seasoned Personality Development , public speaking trainer. Have trained many professionals working in Microsoft, Google and many top MNCs.",
    active: true,
  },
]);
const isScrollable = ref(false);
const showRightIndicator = ref(false);
const checkScrollable = () => {
  const container = document.getElementById("event-container");
  isScrollable.value = container.scrollWidth > container.clientWidth;
  showRightIndicator.value =
    container.scrollLeft < container.scrollWidth - container.clientWidth;
};

const scrollLeft = () => {
  const container = document.getElementById("event-container");
  container.scrollBy({ left: -400, behavior: "smooth" });
};

const scrollRight = () => {
  const container = document.getElementById("event-container");
  container.scrollBy({ left: 400, behavior: "smooth" });
};

onMounted(() => {
  checkScrollable();
  window.addEventListener("resize", checkScrollable);
});

onUnmounted(() => {
  window.removeEventListener("resize", checkScrollable);
});
</script>
<style scoped>
#event-container {
  /* position: relative; */
  background-color: white;
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
.scroll-icon {
  width: 10px;
  height: 10px;
  border-top: 3px solid white;
  border-right: 3px solid white;
  transform: rotate(45deg);
  font-weight: bolder;
}
.scroll-iconleft {
  width: 10px;
  height: 10px;
  border-top: 3px solid white;
  border-right: 3px solid white;
  transform: rotate(225deg);
  font-weight: bolder;
}
.btn {
  position: absolute;
  width: 40px;
  height: 40px;
  padding: 10px;
  border: none;
  border-radius: 50%;
  z-index: 10px;
  cursor: pointer;
  background-color: rgb(126, 126, 235);
  font-size: 18px;
}
.btn-prev {
  top: 50%;
  left: 0;
}
.btn-next {
  top: 50%;
  right: 0;
}
</style>
