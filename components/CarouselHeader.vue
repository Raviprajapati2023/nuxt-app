<template>
  <div class="py-8">
    <div class="slider">
      <div class="slide" v-for="(slide, index) in galleryList" :key="index">
        <img
          :src="currentSlide.imageURL"
          :alt="slide.title"
          class="rounded mx-auto"
        />
        <div class="bottom-div bttm" v-if="currentSlide.title">
          <div class="text-white text-center bg-gray-500">
            <div class="mt-2 text-lg font-bold">{{ currentSlide.title }}</div>
            <div class="text-sm">{{ currentSlide.description }}</div>
          </div>
        </div>
      </div>
      <button class="btn btn-next" @click="nextSlide">
        <div class="scroll-icon"></div>
      </button>
      <button class="btn btn-prev" @click="prevSlide">
        <div class="scroll-iconleft"></div>
      </button>
    </div>
  </div>
</template>

<script setup>
import { ref, onBeforeUnmount } from "vue";
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

// Initial slide index
const curSlide = ref(0);

const currentSlide = computed(() => {
  return galleryList.value[curSlide.value];
});
const nextSlide = () => {
  curSlide.value = (curSlide.value + 1) % galleryList.value.length;
};

const prevSlide = () => {
  curSlide.value =
    (curSlide.value - 1 + galleryList.value.length) % galleryList.value.length;
};

const intervalId = setInterval(nextSlide, 4000);

// Clear the interval when the component is unmounted
onBeforeUnmount(() => {
  clearInterval(intervalId);
});
</script>

<style scoped>
.slider {
  width: 100%;
  height: 500px;
  position: relative;
  overflow: hidden; /* <===  */
  border-radius: 15px;
}

.slide {
  width: 100%;
  height: 450px;
  position: absolute;
  transition: all 0.5s;
}

.slide img {
  width: auto;
  height: 100%;
  /* object-fit: cover; */
  border-radius: 20px;
  /* margin: 0px 50px 0px 50px; */
  margin: auto;
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
  background-color: rgb(87, 87, 89);
  font-size: 18px;
}
.bttm {
  position: absolute;
  width: 100%;
  /* height: auto; */
  /* padding: 5px; */
  border: none;
  /* border-radius: 10px; */
  z-index: 5000;
  /* background-color: rgb(87, 87, 89); */
  /* font-size: 18px; */
}

.bottom-div {
  bottom: 0;
  height: auto;
}
.btn:active {
  transform: scale(1.1);
}
.btn-prev {
  top: 45%;
  left: 2%;
}

.btn-next {
  top: 45%;
  right: 2%;
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
</style>
