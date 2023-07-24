<template>
  <div class="container mx-auto px-4">
    <div class="h-screen flex justify-center flex-col">
      <p class="text-blue-200 mb-5">Hi, my name is</p>
      <h1 class="heading-text text-pink-400 mb-5">Yoswaris Lawpaiboon</h1>
      <h2 class="text-2xl text-blue-100 mb-5">One night miracle is real !</h2>
      <h3 class="md:w-1/2 mb-5 text-space">I am a web developer passionate about creating intuitive and engaging user experiences. With several years of experience in web development, I have honed my skills in creating dynamic websites and applications using a range of programming languages and technologies.</h3>
      <!-- <button class="p-4 gradient-border cursor-pointer">Check out my project !</button> -->
    </div>

    <div class="xl:h-screen">
      <div class="xl:h-[50vh]">
        <p class="mb-3 text-2xl text-violet-300 inline">About Me!</p>

        <div class="xl:flex flex-row">
          <div class="w-full xl:w-1/2">
            <p class="mb-3 text-space">Hi there! I'm <span class="text-orange-300">Yoswaris Lawpaiboon</span>, and I have a passion for coding. My interest in web development started in 2016 when I learned from youtube and the web board how to build websites from scratch. My initial motivation was to sell C source code to my friends by creating a website. Since then, I've continued to learn and grow as a developer, always looking for a new Tech stack.</p>
          
            <p class="mb-5">I always try to change the world with new ideas.</p>
            
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

          <div class="w-full xl:w-1/2">
            <div class="mt-20 xl:m-20 rounded p-5 bg-slate-700">
              <p>
                Stats from
                <a :href="`https://github.com/${githubUserStats.login}`" class="text-pink-300 hover:text-pink-400">My Github</a>
              </p>
              <div v-if="githubUserStats.isLoading">
                <p class="text-gray-400" v-if="githubUserStats.isError">
                  An error occurred while loading, Go check
                  <a :href="`https://github.com/${githubUserStats.login}`" class="text-pink-300 hover:text-pink-400">My Github</a>
                </p>
                <p class="text-gray-400" v-else>Loading...</p>
              </div>
              <div class="mt-3" v-else>
                <div class="w-full xl:flex flex-row justify-center">
                  <div class="w-fit mb-5 xl:mr-5 mx-auto">
                    <img :src="githubUserStats.avatar_url" :alt="`${githubUserStats.login}`" class="rounded-full w-20 h-20 mx-auto">
                    <p class="text-center">
                      <a :href="`https://github.com/${githubUserStats.login}`" class="text-pink-300 hover:text-pink-400">{{ githubUserStats.login }}</a>
                    </p>
                  </div>
                  <div class="grid grid-cols-12 gap-5">
                    <div class="col-span-12 sm:col-span-6">
                      <p class="text-2xl text-orange-300">{{ githubUserStats.public_repos }}</p>
                      <p class="text-gray-400">Repositories</p>
                    </div>
                    <div class="col-span-12 sm:col-span-6">
                      <p class="text-2xl text-orange-300">{{ githubUserStats.followers }}</p>
                      <p class="text-gray-400">Followers</p>
                    </div>
                    <div class="col-span-12 sm:col-span-6">
                      <p class="text-2xl text-orange-300">{{ githubUserStats.location }}</p>
                      <p class="text-gray-400">Location</p>
                    </div>
                    <div class="col-span-12 sm:col-span-6">
                      <p class="text-2xl text-orange-300">{{ githubUserStats.hireable ? 'Yes, Hire me!' : 'No, sorry' }}</p>
                      <p class="text-gray-400">Hireable</p>
                    </div>
                    <!-- <div class="col-span-12 mt-2">
                      <p>Stats from my repo.</p>
                      <div v-if="githubRepoStats.isLoading">
                        <p class="text-gray-400" v-if="githubRepoStats.isError">
                          An error occurred while loading, Go check
                          <a :href="`https://github.com/${githubUserStats.login}?tab=repositories`" class="text-pink-300 hover:text-pink-400">My Github repo.</a>
                        </p>
                        <p class="text-gray-400" v-else>Loading...</p>
                      </div>
                      <div class="grid grid-cols-12 gap-5" v-else>
                        <div class="col-span-6" v-for="(value, index) in githubRepoStats.languages" :key="index">
                          <p class="text-2xl text-orange-300">{{ value }}</p>
                          <p class="text-gray-400">{{ index }}</p>
                        </div>
                      </div>
                    </div> -->
                  </div>
                </div>
              </div>
            </div>
          </div>
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

<script lang="ts">
  export default {
    // state
    data() {
      return {
        githubUsername: 'kiznick',
        githubUserStats: {
          isLoading: true,
          isError: false,
          login: this.githubUsername,
          avatar_url: 'https://cdn.kiznick.in.th/logo/logo-gold-japan.png',
          public_repos: 0,
          followers: 0,
          hireable: true,
          location: 'Bangkok, Thailand',
          repos_url: 'https://api.github.com/users/kiznick/repos'
        },
        // githubRepoStats: {
        //   isLoading: true,
        //   isError: false,
        //   languages: {}
        // },
        year: new Date().getFullYear(),
      }
    },
    mounted() {
      this.fetchGithubUserStats()
    },
    methods: {
      async fetchGithubUserStats() {
        const response = await fetch(`https://api.github.com/users/${this.githubUsername}`)

        if (!response.ok) {
          return this.githubUserStats.isError = true
        }

        const data = await response.json()
        this.githubUserStats = data

        // this.fetchGithubRepoStats()
      },

      // async fetchGithubRepoStats() {
      //   const response = await fetch(this.githubUserStats.repos_url)

      //   if (!response.ok) {
      //     return this.githubRepoStats.isError = true
      //   }

      //   const data = await response.json()
      //   // this.githubRepoStats = data

      //   let languages: Record<string, number> = {}

      //   data.map((value: any) => {
      //     if (value.language) {
      //       if (languages[value.language]) {
      //         languages[value.language] += 1
      //       } else {
      //         languages[value.language] = 1
      //       }
      //     }
      //   })

      //   this.githubRepoStats.isLoading = false
      //   this.githubRepoStats.languages = languages
      // },
    }
  }

  useServerSeoMeta({
    title: 'Yoswaris Lawpaiboon',
    ogTitle: 'Yoswaris Lawpaiboon',
    description: 'Yoswaris Lawpaiboon\'s Portfolio',
    ogDescription: 'Yoswaris Lawpaiboon\'s Portfolio',
    // ogImage: 'https://example.com/image.png',
    twitterCard: 'summary_large_image',
  })

  // const year = new Date().getFullYear()

  // const githubUsername = 'kiznick'

  // type GithubStats = {
  //   avatar_url: string
  //   public_repos: number
  //   followers: number
  //   repos_url: string
  // }

  // const { pending, data: githubStats } = useLazyFetch<GithubStats>('https://api.github.com/users/' + githubUsername)
  // watch(githubStats, (data) => {
  //   githubStats.followers = '50'

  // })
</script>
