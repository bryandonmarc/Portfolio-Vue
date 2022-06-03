<script setup lang="ts">
const { t, availableLocales, locale } = useI18n()
const user = useUserStore()
const router = useRouter()
const toggleLocales = () => {
  // change to some real logic
  const locales = availableLocales
  locale.value = locales[(locales.indexOf(locale.value) + 1) % locales.length]
}
</script>

<template>
  <div>
    <nav text-xl mt-24>
      <RouterLink class="icon-btn mx-2" to="/" :title="t('button.home')">
        <div i-carbon-campsite />
      </RouterLink>
      <button class="icon-btn mx-2 !outline-none" :title="t('button.toggle_dark')" @click="toggleDark()">
        <div i="carbon-sun dark:carbon-moon" />
      </button>
      <a class="icon-btn mx-2" :title="t('button.toggle_langs')" @click="toggleLocales()">
        <div i-carbon-language />
      </a>
      <!-- <RouterLink class="icon-btn mx-2" to="/about" :title="t('button.about')">
        <div i-carbon-dicom-overlay />
      </RouterLink> -->
      <a class="icon-btn mx-2" rel="noreferrer" href="https://github.com/bryandonmarc" target="_blank" title="GitHub">
        <div i-carbon-logo-github />
      </a>
      <a class="icon-btn mx-2" rel="noreferrer" href="https://www.linkedin.com/in/donmarc-bryan-salcedo-7169541b6/" target="_blank" title="GitHub">
        <div i-carbon-logo-linkedin />
      </a>
      <a class="icon-btn mx-2" rel="noreferrer" href="mailto:bryan.donmarc@gmail.com" target="_blank" title="GitHub">
        <div i-carbon-email />
      </a>
    </nav>
    <div v-if="router.currentRoute.value.path !== '/'" class="flex flex-col items-center text-center text-sm mt-4">
      <span>Built with <a href="https://github.com/antfu/vitesse" target="_blank" class="link link-primary no-underline hover:underline font-semibold">Vitesse</a></span>
      <span>Designed and developed by {{ user.userName }}.</span>
      <span>Inspired by <a class="link link-primary no-underline hover:underline font-semibold" href="https://abdulrahman.id/" target="_blank">Abdul Rahman</a></span>
    </div>
  </div>
</template>
