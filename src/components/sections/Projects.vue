<script setup lang="ts">
const projects = [
  {
    title: 'RENU Naturals',
    url: 'https://renunaturals.com/',
    imgUrl: 'https://cdn.shopify.com/s/files/1/0368/5210/5356/files/aaaaa.png?v=1649238433',
    badges: [{
      name: 'Shopify',
      class: 'bg-[color:#95BF46]/15 text-[color:#95BF46]',
      iconClass: 'i-logos-shopify',
    }, {
      name: 'AlpineJS',
      class: 'bg-[color:#77C1D2]/15 text-[color:#77C1D2]',
      iconClass: 'i-logos-alpinejs-icon',
    }, {
      name: 'TailwindCSS',
      class: 'bg-[color:#0EA5E9]/15 text-[color:#0EA5E9]',
      iconClass: 'i-logos-tailwindcss-icon',
    }, {
      name: 'PWA',
      class: 'bg-[color:#5A0FC8]/15 text-[color:#5A0FC8]',
      iconClass: 'i-logos-pwa',
    }],
    description: 'A skincare beauty brand featuring natural cruelty-free and vegan skincare products, made and infused with the highest quality organic ingredients and botanical extracts, herbs and oils.',
  },
  {
    title: '1220 Candle Co.',
    url: 'https://1220candlecompany.com/',
    imgUrl: 'https://cdn.shopify.com/s/files/1/0603/4659/7552/files/social_sharing.png',
    badges: [{
      name: 'Shopify',
      class: 'bg-[color:#95BF46]/15 text-[color:#95BF46]',
      iconClass: 'i-logos-shopify',
    }, {
      name: 'AlpineJS',
      class: 'bg-[color:#77C1D2]/15 text-[color:#77C1D2]',
      iconClass: 'i-logos-alpinejs-icon',
    }, {
      name: 'PostCSS',
      class: 'bg-[color:#DD3735]/15 text-[color:#DD3735]',
      iconClass: 'i-logos-postcss',
    }, {
      name: 'Google Analytics',
      class: 'bg-[color:#F9AB00]/15 text-[color:#F9AB00]',
      iconClass: 'i-logos-google-analytics',
    }],
    description: '1220 Candle Company is a Mississippi based candle company with a mission to simply create luxury candles with alluring aromas and fragrances, luscious and moisturizing body butters, sensuous room sprays, and captivating wax melts.',
  },
  {
    title: 'eduGames Teach',
    url: 'https://edu-tech-ssr.herokuapp.com/',
    localImage: true,
    imgUrl: '../../assets/eduGames Teach Presentation 2.0.jpg',
    badges: [{
      name: 'Nuxt',
      class: 'bg-[color:#00DC82]/15 text-[color:#00DC82]',
      iconClass: 'i-logos-nuxt-icon',
    }, {
      name: 'Vue',
      class: 'bg-[color:#41B883]/15 text-[color:#41B883]',
      iconClass: 'i-logos-vue',
    }, {
      name: 'Node.js',
      class: 'bg-[color:#84ba64]/15 text-[color:#84ba64]',
      iconClass: 'i-logos-nodejs-icon',
    }, {
      name: 'Unity',
      class: 'bg-[color:#222C37]/15 text-[color:#222C37] dark:bg-[#fff]/5 dark:text-[#fff]',
      iconClass: 'i-logos-unity',
    }, {
      name: 'Heroku',
      class: 'bg-[color:#430098]/15 text-[color:#430098]',
      iconClass: 'i-logos-heroku-icon',
    }],
    description: 'Experience a new way of learning for your students using this teaching companion service featuring gamified learning with a fun, interactive educational game!',
  },
  {
    title: 'MCL COVID19 Case Tracker for Laguna',
    url: 'https://mcl-covid19tracker-laguna.netlify.app/',
    imgUrl: 'https://mcl-covid19tracker-laguna.netlify.app/banner.jpg',
    badges: [{
      name: 'Nuxt',
      class: 'bg-[color:#00DC82]/15 text-[color:#00DC82]',
      iconClass: 'i-logos-nuxt-icon',
    }, {
      name: 'Sass',
      class: 'bg-[color:#BF4080]/15 text-[color:#BF4080]',
      iconClass: 'i-logos-sass',
    }, {
      name: 'ApexCharts.js',
      class: 'bg-[color:#222C37]/15 text-[color:#222C37] dark:bg-[#fff]/5 dark:text-[#fff]',
      iconClass: 'i-carbon-code',
    }, {
      name: 'Python',
      class: 'bg-[color:#FBD38D]/15 text-[color:#FBD38D]',
      iconClass: 'i-logos-python',
    }, {
      name: 'Netlify',
      class: 'bg-[color:#37B0BB]/15 text-[color:#37B0BB]',
      iconClass: 'i-logos-netlify',
    }],
    description: 'COVID19 Dashboard and Case Tracker for Laguna, tracking health cases and reports from the city/municipality down to the barangay/district level. Developed by MCL College of Computer and Information Science.',
  },
]
</script>

<template>
  <section class="max-w-[1536px] w-full mx-auto mt-36 flex flex-col lg:flex-row gap-8 px-8">
    <div class="flex flex-col gap-8 w-full">
      <div class="flex flex-col text-sm justify-start items-start" xs="text-lg" sm="text-2xl" lg="text-3xl">
        <h1 class="flex items-center text-3xl mb-4" xs="text-4xl" sm="text-5xl">
          Projects
          <div i-carbon-star-filled class="ml-2 text-primary fill-current" />
        </h1>
        <p dark="text-gray-400">
          Here are some of the projects I've worked on
        </p>
      </div>
      <ProjectCard v-for="(item, index) in projects.filter((e, i) => i % 2)" :key="index" :item="item" />
    </div>
    <div class="flex flex-col gap-8 w-full">
      <ProjectCard v-for="(item, index) in projects.filter((e, i) => !(i % 2))" :key="index" :item="item" />
    </div>
  </section>
</template>

<style scoped>

</style>
