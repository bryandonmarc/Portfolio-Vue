<script setup lang="ts">
const { t, availableLocales, locale } = useI18n()
const user = useUserStore()
const router = useRouter()

const toggleLocales = () => {
  // change to some real logic
  const locales = availableLocales
  locale.value = locales[(locales.indexOf(locale.value) + 1) % locales.length]
}

const navbar = ref(null)

onMounted(() => {
  const prevScrollpos = ref(window.pageYOffset)
  window.onscroll = function () {
    const currentScrollPos = window.pageYOffset

    if (prevScrollpos.value > currentScrollPos)
      navbar.value.style.top = '0'
    else
      navbar.value.style.top = '-73px'

    prevScrollpos.value = currentScrollPos
  }
})
</script>

<template>
  <Transition name="slide-fade" appear>
    <nav ref="navbar" :class="[isDark.value ? 'bg-[color:#121212]' : 'bg-white']" class="navbar py-3 px-4 border-b border-light-800 fixed top-0 transition-all ease-in-out z-10" sm="px-14" dark="border-dark-400">
      <div class="flex-1">
        <RouterLink v-if="router.currentRoute.value.path !== `/welcome/${user.savedName}`" class="btn btn-ghost btn-circle normal-case text-xl" :to="`/welcome/${user.savedName}`" :title="t('button.home')">
          <div i-carbon-code />
        </RouterLink>
        <a v-else href="#main" class="btn btn-ghost btn-circle normal-case text-xl">
          <div i-carbon-code />
        </a>
      </div>
      <div class="flex-none text-gray-700" dark="text-gray-200">
        <ul class="menu menu-horizontal p-0">
          <li>
            <RouterLink class="btn btn-ghost mx-2" to="/journey" :title="t('button.about')">
              <i sm:hidden i-carbon-flag />
              <span hidden sm:block>Journey</span>
            </RouterLink>
          </li>
          <li>
            <RouterLink class="btn btn-ghost mx-2" to="/certifications" :title="t('button.about')">
              <i sm:hidden i-carbon-certificate />
              <span hidden sm:block>Certifications</span>
            </RouterLink>
          </li>
          <div class="dropdown dropdown-end ">
            <label tabindex="0" class="btn btn-ghost btn-circle">
              <div i-carbon-settings />
            </label>
            <ul tabindex="0" class="menu menu-compact gap-2 dropdown-content mt-6 p-2 shadow bg-base-100 rounded-box text-gray-200">
              <li>
                <button class="btn btn-ghost mx-2 !outline-none text-lg" :title="t('button.toggle_dark')" @click="toggleDark()">
                  <div i="carbon-sun dark:carbon-moon" />
                </button>
              </li>
              <li>
                <button class="btn btn-ghost mx-2 text-lg" :title="t('button.toggle_langs')" @click="toggleLocales()">
                  <div i-carbon-language />
                </button>
              </li>
            </ul>
          </div>
        </ul>
      </div>
    </nav>
  </Transition>
</template>

<style scoped>
.slide-fade-enter-active {
  transition: all 0.5s ease-in;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateY(-100%);
  opacity: 0;
}
</style>
