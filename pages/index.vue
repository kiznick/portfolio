<script setup lang="ts">
import { ClientOnly } from '~~/.nuxt/components';

  useServerSeoMeta({
    title: 'Yoswaris Lawpaiboon',
    ogTitle: 'Yoswaris Lawpaiboon',
    description: 'Yoswaris Lawpaiboon\'s Portfolio',
    ogDescription: 'Yoswaris Lawpaiboon\'s Portfolio',
    // ogImage: 'https://example.com/image.png',
    twitterCard: 'summary_large_image',
  })
  const year = new Date().getFullYear()
</script>

<template>
  <div class="container mx-auto px-4">
    <div class="h-screen flex justify-center flex-col">
      <p class="text-blue-200 mb-5">Hi, my name is</p>
      <h1 class="heading-text text-pink-400 mb-5">Yoswaris Lawpaiboon</h1>
      <h2 class="text-2xl text-blue-100 mb-5">One night miracle is real !</h2>
      <h3 class="xl:w-1/2 mb-5 text-space">I am a web developer with a passion for creating intuitive and engaging user experiences. With several years of experience in web development, I have honed my skills in creating dynamic websites and applications using a range of programming languages and technologies.</h3>
      <!-- <button class="p-4 gradient-border cursor-pointer">Check out my project !</button> -->
    </div>

    <div class="md:h-screen">
      <div class="md:h-[50vh]">
        <p class="mb-3 text-2xl text-violet-300">About Me!</p>
        <div class="xl:w-1/2">
          <p class="mb-3 text-space">Hi there! I'm <span class="text-orange-300">Yoswaris Lawpaiboon</span> and I have a passion for coding. My interest in web development started in 2016 when I learned from youtube and web board how to build websites from scratch. In fact, my initial motivation was to sell C source code to my friends by creating a website. Since then, I've continued to learn and grow as a developer, always looking for a new Tech stack.</p>
        
          <p class="mb-5">I am always trying to change the world with new ideas.</p>
          
          <p class="mb-3">There are a few technologies I’ve been working with recently:</p>
          <ul class="list-square columns-3 ml-5">
            <li>PHP</li>
            <li>JavaScript</li>
            <li>TypeScript</li>
            <li>NodeJS</li>
            <li>React</li>
            <li>NextJS</li>
            <li>Vue</li>
            <li>NuxtJS</li>
            <li>JQuery</li>
          </ul>
        </div>
      </div>
      <div class="h-[50vh] flex justify-center flex-col">
        <type-it />
      </div>
    </div>

    <div class="my-5">
      <p class="text-center">Copyright &copy; {{ year }} Yoswaris Lawpaiboon</p>
    </div>

    <div class="fixed bottom-0 right-0 m-4 text-xs text-gray-500">
      <a target="_blank" href="https://facebook.com/kiznick">
        <nuxt-img class="mx-2 w-[32px] h-[32px] mb-2" src="~/assets/images/f_logo_RGB-Blue_512.png" alt="facebook.com/kiznick" placeholder quality="100" width="32" height="32" />
      </a>
      <a target="_blank" href="https://github.com/kiznick">
        <nuxt-img class="mx-2 w-[32px] h-[32px]" src="~/assets/images/github-mark-white.svg" alt="github.com/kiznick" placeholder quality="100" width="32" height="32" />
      </a>
    </div>
  </div>
</template>