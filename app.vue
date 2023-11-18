<template>
   <NuxtLayout :name="layout" >
    <index />
  </NuxtLayout>
    
   
</template>
<script setup>
const layout = "default";
import index from "@/public/pages/index.vue"
</script>