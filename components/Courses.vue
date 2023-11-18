<template>
    <div>
      <h2 class="text-2xl font-bold tracking-tight text-gray-900 my-8 text-center"> Popular Courses</h2>
     
      <div class="sm:hidden">
        <label for="tabs" class="sr-only">Select a tab</label>
        <select
          id="tabs"
          name="tabs"
          class="block w-full rounded-md border-gray-300 focus:border-indigo-500 focus:ring-indigo-500"
          v-model="selectedTab"
        >
          <option
            v-for="tab in tabs"
            :key="tab.name"
            :value="tab.name"
          >
            {{ tab.name }}
          </option>
        </select>
      </div>
      <div class="hidden sm:block">
        <nav class="isolate flex divide-x divide-gray-200 rounded-lg shadow" aria-label="Tabs">
          <a
            v-for="(tab, tabIdx) in tabs"
            :key="tab.name"
            :href="tab.href"
            @click="selectTab(tab.name)"
            :class="[
              selectedTab === tab.name ? 'text-gray-900' : 'text-gray-500 hover:text-gray-700',
              tabIdx === 0 ? 'rounded-l-lg' : '',
              tabIdx === tabs.length - 1 ? 'rounded-r-lg' : '',
              'group relative min-w-0 flex-1 overflow-hidden bg-white py-4 px-4 text-center text-sm font-medium hover:bg-gray-50 focus:z-10',
            ]"
            :aria-current="selectedTab === tab.name ? 'page' : undefined"
          >
            <span>{{ tab.name }}</span>
            <span
              aria-hidden="true"
              :class="[selectedTab === tab.name ? 'bg-indigo-500' : 'bg-transparent', 'absolute inset-x-0 bottom-0 h-0.5']"
            />
          </a>
        </nav>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const selectedTab = ref('FSD');
  const tabs = [
    { name: 'Job Oriented', href: '#' },
    { name: 'FSD', href: '#' },
    { name: 'Front-End', href: '#' },
    { name: 'Android', href: '#' },
    { name: 'Programming', href: '#' },
  ];
  
  const selectTab = (tabName) => {
    selectedTab.value = tabName;
  };
  </script>
  