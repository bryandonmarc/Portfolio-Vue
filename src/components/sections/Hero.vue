<script setup lang="ts">
const props = defineProps<{ name: string }>()
const user = useUserStore()
const { t } = useI18n()
</script>

<template>
  <section class="hero mt-[20vh] px-4">
    <div class="hero-content max-w-[1536px] w-full text-left relative">
      <HeroPattern class="w-36 h-36 absolute text-gray-200 -z-1 -left-12 -top-3 opacity-15" dark="opacity-100 invert-[0.15]" />
      <div class="w-full flex flex-col gap-y-8">
        <h1 class="font-bold text-3xl">
          <span class="text-primary">{{ t('intro.hi', { name: props.name }) }}</span> My name is
          <br>
          <TypewriterText
            class="text-5xl" xs="text-6xl" sm="text-7xl" lg="text-8xl" xl="text-9xl" :text="user.userName"
          />
        </h1>

        <VerticalScrollingText
          :titles="['Computer Scientist', 'Web Developer', 'Tech Enthusiast',
                    'Student Researcher', 'Latin Honor Candidate', 'Shopify Developer',
                    'Full Stack Developer', 'Student Leader', 'Software Engineer']"
        >
          <br>
          <span dark="text-gray-400">A self-taught developer with a passion for knowledge and curiosity to learn even more!</span>
        </VerticalScrollingText>

        <div class="pl-4 border-l-3 border-primary text-sm" xs="text-lg" sm="text-2xl" lg="text-3xl" dark="text-gray-400">
          <p>
            🚀 Exploring opportunities and side projects
          </p>
          <p class="flex flex-row flex-wrap flex-shrink-0">
            💻 Currently building beautiful <span i-logos-shopify ml-2 mr-1 /> Shopify themes at&nbsp;
            <a
              href="https://artologie.co/" target="_blank" rel="noreferrer noopener"
              class="link text-pink-400 hover:text-pink-500" dark="text-pink-200 hover:text-pink-300"
            >Artologie</a>
          </p>
        </div>

        <div flex flex-row flex-wrap gap-4>
          <a
            href="https://github.com/bryandonmarc" target="_blank" rel="noreferrer noopener"
            class="btn btn-ghost gap-2 bg-light-200 btn-sm" sm="btn-md" dark="bg-dark-300"
          > <i i-logos-github-icon /> Github</a>
          <a
            href="https://www.linkedin.com/in/donmarc-bryan-salcedo-7169541b6/" target="_blank" rel="noreferrer noopener"
            class="btn btn-ghost gap-2 bg-light-200 btn-sm" sm="btn-md" dark="bg-dark-300"
          > <i i-logos-linkedin-icon /> LinkedIn</a>
          <a
            href="../../assets/SALCEDO - Competency-based Resume V2.pdf" download="SALCEDO - Competency-based Resume.pdf" rel="noreferrer noopener"
            class="btn btn-ghost gap-2 bg-light-200 btn-sm" sm="btn-md" dark="bg-dark-300"
          > <i i-carbon-download /> Resume</a>
        </div>
      </div>
    </div>
  </section>
</template>
