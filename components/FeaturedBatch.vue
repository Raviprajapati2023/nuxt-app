<template>
  <section class="py-12 px-4">
    <div class="max-w-screen-xl mx-auto px-2 md:px-8">
      <div class="bg-white">
        <h3
          class="text-gray-800 text-3xl my-8 w-full font-bold sm:text-4xl text-center"
        >
          FEATURED BATCHES
        </h3>
        <div>
          <ul class="mt-4 grid gap-4  sm:grid-cols-1 md:grid-cols-3">
            <li
              v-for="batch in batchList"
              :key="batch.name"
              class="border rounded-xl bg-white hover:border-light-blue-500 hover:border-opacity-25 cursor-pointer hover:shadow-lg"
            >
              <div class="p-4">
                <h3 class="text-xl font-semibold mb-2">
                  {{ batch.name }} By {{ batch.facultyName }}
                </h3>
                <p class="text-gray-500 text-base my-2">
                  {{ batch.description }}
                </p>

                <div class="flex items-center my-6">
                  <div class="mr-2">
                    <!-- <img
                      src="https://www.batchbeep.in/img/calendar.cac65f37.svg"
                      class="w-6 h-6"
                    /> -->
                  </div>
                  <div class="text-gray-600">{{ batch.batchStartDate }}</div>
                </div>
                <div class="flex items-center my-6">
                  <div class="mr-2">
                    <!-- <img
                      src="https://www.batchbeep.in/img/location.a8fc849d.svg"
                      class="w-6 h-6"
                    /> -->
                  </div>
                  <div class="text-gray-600">{{ batch.branchName }}</div>
                </div>
                <div class="flex items-center my-6">
                  <div class="mr-2">
                    <!-- <img
                      src="https://www.batchbeep.in/img/clock.8cedf1a4.svg"
                      class="w-6 h-6"
                    /> -->
                  </div>
                  <div class="text-gray-600">
                    {{ batch.batchTiming }}
                  </div>
                </div>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>
<script setup>
import { ref } from "vue";

const batchList = ref([
  {
    name: "A1",
    courseName: "Full Stack Development",
    facultyName: "Rishi",
    batchStartDate: 1672966800000,
    batchTiming: "5:00 PM   to   6:30 PM   -  MTWTF",
    branchName: "B/173, Shruti Kunj",
    description: "Job oriented course ",
    active: true,
    batchURL: null,
  },
  {
    name: "A2",
    courseName: "Full Stack Development",
    facultyName: "Rishi",
    batchStartDate: 1676284200000,
    batchTiming: "5:00 PM   to  06:30  -   MTWTF",
    branchName: "B/173, Shruti Kunj",
    description: "Guaranteed Job",
    active: true,
    batchURL: null,
  },
  {
    name: "A3",
    courseName: "Full Stack Development",
    facultyName: "Rishi",
    batchStartDate: 1677222000000,
    batchTiming: "6:30 PM    to  08:00  -    MTWTF",
    branchName: "B/173, Shruti Kunj",
    description: "Guaranteed Job",
    active: true,
    batchURL: null,
  },
  {
    name: "A4",
    courseName: "Full Stack Development",
    facultyName: "Rishi",
    batchStartDate: 1678858200000,
    batchTiming: "3:30 PM  to  5:30 PM  -  MTWTF",
    branchName: "B/173, Shruti Kunj",
    description: "Guaranteed Job",
    active: true,
    batchURL: null,
  },
  {
    name: "A5",
    courseName: "Full Stack Development",
    facultyName: "Rishi",
    batchStartDate: 1680613200000,
    batchTiming: "9:00 AM to 11:00 AM - MTWTFS",
    branchName: "B/173, Shruti Kunj",
    description: "Batch start from 25th March 23",
    active: true,
    batchURL: null,
  },
  {
    name: "A4-B",
    courseName: "Introduction to Programming with C/C++/Java/Python",
    facultyName: "Rishi",
    batchStartDate: 1681797600000,
    batchTiming: "10:00 AM to 12:00 PM - MTWTFSS",
    branchName: "B/173, Shruti Kunj",
    description: "Introduction to Programming",
    active: true,
    batchURL: null,
  },
  {
    name: "A6",
    courseName: "Full Stack Development",
    facultyName: "Rishi",
    batchStartDate: 1683399600000,
    batchTiming: "04:00 to 06:00 - MTWTFS",
    branchName: "B/173, Shruti Kunj",
    description: "Full stack",
    active: true,
    batchURL: null,
  },
  {
    name: "A-6 S",
    courseName: "Single language A",
    facultyName: "Rishi",
    batchStartDate: 1683964800000,
    batchTiming: "4:00 PM to 5:30 PM - ",
    branchName: "B/173, Shruti Kunj",
    description: "Introduction to Programming",
    active: true,
    batchURL: null,
  },
  {
    name: "Boring road",
    courseName: "Full Stack Development",
    facultyName: "Rishi",
    batchStartDate: 1683945000000,
    batchTiming: "00:00 to null - MTWTFS",
    branchName: "1267, G-1, First Floor,",
    description: "Boring road",
    active: true,
    batchURL: null,
  },
  {
    name: "A7 -s",
    courseName: "Single language B",
    facultyName: "Rishi",
    batchStartDate: 1686517200000,
    batchTiming: "18:00 to 20:00 - MTWTF",
    branchName: "B/173, Shruti Kunj",
    description: "Java single course",
    active: true,
    batchURL: null,
  },
  {
    name: "A7",
    courseName: "Full Stack Development",
    facultyName: "Rishi",
    batchStartDate: 1686517200000,
    batchTiming: "11:00 to 01:00 - MTWTF",
    branchName: "B/173, Shruti Kunj",
    description: "Full stack developer batch",
    active: true,
    batchURL: null,
  },
  {
    name: "A8",
    courseName: "Job Oriented - Full Stack Development",
    facultyName: "Rishi",
    batchStartDate: 1689913800000,
    batchTiming: "16:00 to 19:00 - MWFS",
    branchName: "B/173, Shruti Kunj",
    description: "Job oriented programme",
    active: true,
    batchURL: null,
  },
  {
    name: "A8",
    courseName: "Job Oriented - Full Stack Development",
    facultyName: "Rishi",
    batchStartDate: 1693031400000,
    batchTiming: "15:00 to 18:00 - MWF",
    branchName: "B/173, Shruti Kunj",
    description: "Job oriented course",
    active: true,
    batchURL: null,
  },
]);
</script>
