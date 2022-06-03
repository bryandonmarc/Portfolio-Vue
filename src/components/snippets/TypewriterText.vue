<script setup lang="ts">
import { onMounted, ref } from 'vue'
const props = defineProps<{ text: string }>()

/*
 * Typing Animation
 */
let i = 0
const txt = props.text /* The text */
const speed = 50 /* The speed/duration of the effect in milliseconds */
const typewriter = ref(null)
const typeWriter = () => {
  if (i < txt.length) {
    typewriter.value.innerHTML += txt.charAt(i)
    i++
    setTimeout(typeWriter, speed)
  }
}
onMounted(() => {
  setTimeout(typeWriter, 1000)
})
</script>

<template>
  <span ref="typewriter" class="typewriter" />
</template>

<style scoped>
.typewriter {
  overflow: hidden; /* Ensures the content is not revealed until the animation */
  border-right: .15em solid hsl(var(--p)/1); /* The typwriter cursor */
  /* white-space: nowrap;  Keeps the content on a single line */
  margin: 0 auto; /* Gives that scrolling effect as the typing happens */
  letter-spacing: .1em; /* Adjust as needed */
  animation:
    typing 3.5s steps(40, end),
    blink-caret .75s step-end infinite;
}

/* The typing effect */
@keyframes typing {
  from { width: 0 }
  to { width: 100% }
}

/* The typewriter cursor effect */
@keyframes blink-caret {
  from, to { border-color: transparent }
  50% { border-color: hsl(var(--p)/1); }
}
</style>
