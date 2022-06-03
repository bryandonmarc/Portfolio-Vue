<script setup lang="ts">
const props = defineProps<{
  array: Array<string>
  reverse: boolean
}>()
</script>

<template>
  <div class="marquee">
    <div :class="[props.reverse ? 'track-reverse' : 'track']">
      <div class="content text-lg" sm="text-xl" lg="text-2xl">
        {{ props.array.concat(props.array).concat(props.array).join("&nbsp;·&nbsp;") }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.marquee {
  position: relative;
  width: 100vw;
  max-width: 100%;
  height: 2.5rem;
  overflow: hidden;
}

.track, .track-reverse {
  position: absolute;
  white-space: nowrap;
  will-change: transform;
}

.track {
  animation: marquee 256s linear infinite;
}

.track-reverse {
  animation: marquee-reverse 256s linear infinite;
}

@keyframes marquee {
  from { transform: translateX(0); }
  to { transform: translateX(-50%); }
}

@keyframes marquee-reverse {
  from { transform: translateX(-50%); }
  to { transform: translateX(0); }
}
</style>
