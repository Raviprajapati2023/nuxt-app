<template>
    <div
      class="space-y-3 mt-5 overflow-hidden border-b"
      @click="handleOpenAnswer"
    >
      <h4 class="cursor-pointer pb-5 flex items-center justify-between text-lg text-gray-700 font-medium">
        {{ faqsList.q }}
        <svg
          v-if="state"
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5 text-gray-500 ml-2"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 12H4" />
        </svg>
        <svg
          v-else
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5 text-gray-500 ml-2"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M12 4v16m8-8H4"
          />
        </svg>
      </h4>
      <div
        ref="answerElRef"
        class="duration-300"
        :style="{ height: state ? answerH : '0px' }"
      >
        <div>
          <p class="text-gray-500">
            {{ faqsList.a }}
          </p>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const answerElRef = ref();
  const state = ref(false);
  const answerH = ref('0px');
  
  const handleOpenAnswer = () => {
    console.log("___________________________get answer");
    const answerElH = answerElRef.value.children[0].offsetHeight;
    state.value = !state.value;
    answerH.value = `${answerElH + 20}px`;
  };
  
  const props = defineProps({
    faqsList: Object,
    idx: Number,
  });
  </script>
  