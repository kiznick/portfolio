<template>
  <div class="h-screen flex justify-center flex-col text-center">
    <div v-if="error.statusCode === 404">
      <h1 class="text-9xl text-red-500">404</h1>
      <h2 class="text-6xl mb-3">Page not found.</h2>
      <p class="text-xl">The page you are looking for does not exist.</p>
      <p class="text-xl">Please check the URL in the address bar and try again.</p>
    </div>
    <div v-else>
      <h1 class="text-9xl text-red-500">{{ error.statusCode }}</h1>
      <h2 class="text-6xl mb-3">An error occurred.</h2>
      <p class="text-xl">Please report to administrator.</p>
    </div>

    <NuxtLink to="/">
      <button class="mt-5 p-4 gradient-border cursor-pointer">Who am I?</button>
    </NuxtLink>
  </div>
</template>

<script lang="ts">
  export default {
    props: ['error'],
    // layout: 'error',
  }

  useHead({
    title: 'Error | Yoswaris Lawpaiboon',
  })
</script>