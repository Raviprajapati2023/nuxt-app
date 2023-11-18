<template>
    <div class="h-12 my-4 mx-8 text-2xl font-semibold text-green-500 ">
      <p>{{ typedText }}</p>
    </div>
  </template>
  
  <script setup>
  import { ref, computed, onMounted } from 'vue';
  
  // eslint-disable-next-line no-magic-numbers
  const ZERO = 0;
  // eslint-disable-next-line no-magic-numbers
  const ONE = 1;
  
  const texts = ref([
    'Effective Performance Tracking',
    'Easy Report Generation ',
    'Hassels free Exam Management',
    'Streaming Admission',
  ]);
  const currentTextIndex = ref(ZERO);
  const typedText = ref('');
  const typingSpeed = 200;
  const currentText = computed(() => texts.value[currentTextIndex.value]);
  
  function typeText() {
    // eslint-disable-next-line no-magic-numbers
    let currentIndex = 0;
    const intervalId = setInterval(() => {
      typedText.value += currentText.value[currentIndex];
      currentIndex += ONE;
      if (currentIndex === currentText.value.length) {
        clearInterval(intervalId);
        if (currentTextIndex.value < texts.value.length - ONE) {
          currentTextIndex.value += ONE;
          typedText.value = '';
          typeText(); // Call the function directly
        } else {
          currentTextIndex.value = ZERO; // Reset back to the first text
          typedText.value = '';
          typeText(); // Call the function directly
        }
      }
    }, typingSpeed);
  }
  
  onMounted(() => {
    typeText();
  });
  </script>
  