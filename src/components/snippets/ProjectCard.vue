<script setup lang="ts">
const props = defineProps<{
  item: PropInterface
}>()

// https://stackoverflow.com/a/71135980
const getLocalImage = (url: string) => {
  return new URL(url, import.meta.url).href
}

interface PropInterface {
  title: string
  url: string
  imgUrl: string
  localImage?: boolean
  badges: Array<BadgeInterface>
  description: string
}

interface BadgeInterface {
  name: string
  class: string
  iconClass: string
}
</script>

<template>
  <a :href="props.item.url" target="_blank" class="card w-full shadow-lg hover:scale-105 transition" :class="[isDark.value ? 'bg-[color:#121212]' : 'bg-white']">
    <figure class="w-full">
      <img class="w-full" :src="props.item.localImage ? getLocalImage(props.item.imgUrl) : props.item.imgUrl">
    </figure>
    <div class="card-body text-left">
      <h2 class="card-title flex flex-row justify-between items-center text-2xl">
        <span>{{ props.item.title }}</span>
        <a :href="props.item.url" target="_blank" class="flex transition-colors hover:text-primary">
          <span i-carbon-launch />
        </a>
      </h2>
      <div class="w-full flex flex-row gap-2 pb-3 border-b border-gray-700/50 flex-wrap" dark="border-gray-200/15">
        <div v-for="(badge, index) in props.item.badges" :key="index" class="badge rounded-md badge-sm border-none py-3.5 font-semibold" xs="badge-md" sm="badge-lg" :class="badge.class">
          <i :class="badge.iconClass" mr-2 />
          {{ badge.name }}
        </div>
      </div>
      <p dark="text-gray-400">
        {{ props.item.description }}
      </p>
    </div>
  </a>
</template>

<style scoped>

</style>
