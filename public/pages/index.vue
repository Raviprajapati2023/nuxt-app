<template>
  <div>
    <AppHeader />
    <CarouselHeader />
    <Registration  id="about-us">
        <TypingEffect />
     </Registration>
    <CoursesCard />
    <!-- <Courses /> -->
    <FacilitySection />
    <FeaturedBatch />
    <!-- <MarketingSection />
     <PlacementCompany /> -->
    <!-- <AnimationComponent /> -->
    <Testimonial />
    <FacultySection />
    <!-- <Gallary /> -->
    <!-- <FaqSection id="faq" /> -->
    <AppFootr :branch-list="form.branchList"/>
  </div>
</template>
<script setup>
import {ref , onMounted } from "vue"
const form = ref({})
const fetchData = async () => {
    try {
    const res = await fetch('https://api.aintrie.in/api/teb/scan/institution/slug/coding-age');
    if (res.ok) {
      const data = await res.json();
      form.value = data.responseObject;
    } else {
      console.error('API request failed with status:', res.status);
    }
  } catch (error) {
    console.error('Error while fetching data:', error);
  }
}

onMounted(()=>{
    fetchData()
})
</script>