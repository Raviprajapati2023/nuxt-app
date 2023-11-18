<template>
    <section class="leading-relaxed  mt-12 mx-auto px-4 ">
      <div class="space-y-3 text-center">
        <h1 class="text-3xl text-gray-800 font-semibold">
          Frequently Asked Questions
        </h1>
        <p class="text-gray-600  mx-auto text-lg">
          Answered all frequently asked questions, Still confused? feel free to contact us.
        </p>
      </div>
      <div class="mt-14 mx-auto">
        <FaqsCard v-for="(item, idx) in faqsList" :key="idx" :faqs-list="item" />
      </div>
    </section>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const faqsList = ref([
  {
    q: "What courses do you offer at your  coding coaching center?",
    a: "We offer a wide range of courses, including programming languages, web development, data science, and more. You can explore our course catalog to find the one that suits your interests and goals."
  },
  {
    q: "How can I enroll  ?",
    a: "To enroll   please visit our 'Online Admission' page and follow the instructions for the admission process. You can also contact our admission office for further assistance."
  },
  {
    q: "What are the qualifications of your teaching staff?",
    a: "Our teaching staff consists of highly qualified and experienced educators with expertise in their respective fields. We ensure that our teachers are well-equipped to provide quality education to our students."
  },
  {
    q: "Do you provide online learning options for coding and programming courses?",
    a: "Yes, we offer online learning options for our coding and programming courses. You can access our online platform to learn and practice from the comfort of your home."
  },
  {
    q: "How can I pay my tuition fees?",
    a: "You can pay your tuition fees through our online payment portal, where we accept various payment methods, including credit/debit cards and online banking. You can also visit our administrative office for in-person payments."
  },
  {
    q: "Is financial aid or scholarships available for students?",
    a: "Yes, we offer financial aid and scholarships to eligible students. Please check our 'Scholarships' page for more information on the application process and eligibility criteria."
  },
  {
    q: "Can I request a demo or trial class before enrolling?",
    a: "Certainly! We offer demo classes for select courses to help you get a feel for our teaching style and curriculum. Contact our support team to schedule a demo class or inquire about trial classes."
  },
  {
    q: "Do you provide job placement assistance for coding and programming graduates?",
    a: "Yes, we have a dedicated career services team that assists our coding and programming graduates in finding job opportunities and internships. We have partnerships with various tech companies for placements."
  }
]);

  </script>