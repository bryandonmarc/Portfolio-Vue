<script setup lang="ts">
const user = useUserStore()
const { t } = useI18n()
</script>

<template>
  <section class="hero mt-16 px-4">
    <div class="hero-content items-center flex-col lg:flex-row-reverse max-w-screen-lg w-full text-left relative">
      <div class="avatar">
        <div class="w-full rounded-full border-2 border-primary">
          <img src="https://api.lorem.space/image/face?hash=3174">
        </div>
      </div>
      <HeroPattern class="w-36 h-36 absolute text-gray-200 -z-1 -right-12 -top-3 opacity-15" dark="opacity-100 invert-[0.15]" />
      <div class="w-full flex flex-col gap-y-8">
        <h1 class="inline-flex items-center mt-4 text-3xl" xs="text-4xl" sm="text-5xl">
          <div i-carbon-boolean class="mr-2 text-primary fill-current" />
          {{ t('button.about') }}
        </h1>

        <div class="space-y-2 text-sm" sm="text-base">
          <p>
            Hallo! I'm {{ user.userName }}. Ever since I was a kid, I've always loved computers and video games, which led me into taking a degree in Computer Science, because it had the word 'computer' in it 😅 But I'm glad I did! It was one of the most satisfying decisions I've ever made.
          </p>
          <p>
            I'm a 4th year graduating student, currently studying Computer Science in MCL. I held leadership positions in our college council and national and international organizations' student chapters that involves the field of computing and ICT. I am a recipient of the OWWA EDSP scholarship, a competitive program that only selects top students across all regions of the Philippines qualified by DOST-SEI. Knowledge is my passion, and programming more so. I am fully competent in various frameworks and languages, and eager and persistent to learn even more!
          </p>
          <p>
            When I'm not coding, I am usually playing games with my friends, hanging out with them, chilling to music, reading novels, or watching Netflix or anime ;)
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>
