<template>
    <div class="bg-white">
  <div class="px-6 py-8">
    <div class="mx-auto max-w-2xl text-center">
      <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Integrated Learning Plateform</h2>
      <h4 class="text-xl  tracking-tight text-black my-4">Your co-pilot for</h4>
      
      <div>
        <slot />
      </div>
      <div class="my-4 flex items-center justify-center gap-x-6">
        <a href="#" class="rounded-md bg-indigo-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Get started</a>
      </div>
    </div>
  </div>
</div>
</template>
  