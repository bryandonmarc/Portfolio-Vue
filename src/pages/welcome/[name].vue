<script setup lang="ts">
const props = defineProps<{ name: string }>()
const user = useUserStore()

watchEffect(() => {
  user.setNewName(props.name)
})
</script>

<template>
  <Hero id="test" :name="props.name" />
  <Marquees />
  <Logos />
  <About />
  <Projects id="test2" />
</template>
