<script setup lang="ts">
import { ref } from 'vue'
const props = defineProps<{ titles: Array<string> }>()

const items = ref(props.titles)
</script>

<template>
  <h2 class="scrolling-words-container text-sm" xs="text-lg" sm="text-2xl" lg="text-3xl">
    <div class="inline-flex items-center">
      <span class="font-semibold">I am a</span>
      <div class="scrolling-words-box">
        <ul>
          <li v-for="(item, index) in items" :key="index" class="font-mono">
            <span class="text-primary">&lt;</span>
            <span>{{ item.replaceAll(' ', '') }}</span>
            <span class="text-primary">&sol;&gt;</span>
          </li>
          <li class="font-mono">
            <span class="text-primary">&lt;</span>
            <span>{{ items[0].replaceAll(' ', '') }}</span>
            <span class="text-primary">&sol;&gt;</span>
          </li>
        </ul>
      </div>
    </div>
    <slot />
  </h2>
</template>

<style scoped lang="scss">
// .color-highlight {
//   background: linear-gradient(to right, currentColor 0% 3.57em, hsl(var(--p)/1) 3.57em 5.36em, currentColor 5.36em 100%);
//   -webkit-background-clip: text;
//   -webkit-text-fill-color: transparent;
// }

.scrolling-words-container {
  display: inline;
  align-items: center;
}

.scrolling-words-box {
  height: 3rem;
  margin: 0;
  overflow: hidden;

  ul {
    margin-left: 0.625rem;
    padding: 0;
    animation: scrollUp 16s infinite;
    animation-delay: 2s;
    li {
      display: flex;
      align-items: center;
      justify-content: flex-start;
      height: 3rem;
      list-style: none;
      font-weight: 400;
    }
  }
}

// Variables
$item-count: 10;

@keyframes scrollUp {
  @for $i from 1 through ($item-count - 1) {
    #{($i * calc(100 / ($item-count - 1))) - calc(calc(100% / $item-count) / 2)}, #{$i * calc(100% / ($item-count - 1))} {
      transform: translateY((calc(-100% / $item-count)) * $i);
    }
  }
}
</style>
