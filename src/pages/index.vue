<script setup lang="ts">
const user = useUserStore()
const name = $ref(user.savedName)

const router = useRouter()
const go = () => {
  if (name)
    router.push(`/welcome/${encodeURIComponent(name)}`)
  else
    router.push(`/welcome/${encodeURIComponent('kind stranger')}`)
}

const { t } = useI18n()
</script>

<template>
  <div class="flex flex-col m-auto w-full gap-y-4 text-left px-8">
    <label
      for="input" class="text-4xl animate-fade-in-down animate-duration-300 animate-count-1"
      xs="text-5xl" sm="text-6xl" lg="text-7xl"
    >
      Nice to meet you! {{ t('intro.whats-your-name') }}
    </label>
    <input
      id="input"
      v-model="name"
      :aria-label="t('intro.whats-your-name')"
      type="text"
      autocomplete="false"
      class="input input-ghost w-full input-lg bg-opacity-75 focus:bg-opacity-0" dark="bg-opacity-50"
      style="background: linear-gradient(hsl(var(--p)/var(--un-bg-opacity)), hsl(var(--p)/var(--un-bg-opacity))) center bottom 10px /calc(100% - 40px) 2px no-repeat;"
      @keydown.enter="go"
    >
    <button class="btn btn-ghost hover:!bg-transparent w-24 place-self-end transition-all ease-in-out duration-250 group relative" @click="go">
      <span class="group-hover:opacity-100 opacity-0 transition-opacity ">Skip</span>
      <span class="text-primary ml-2 h-12 w-12 absolute translate-x-1.5 group-hover:translate-x-10 transition-transform" i-carbon-direction-straight-right />
    </button>
  </div>
</template>

<route lang="yaml">
meta:
  layout: home
</route>
