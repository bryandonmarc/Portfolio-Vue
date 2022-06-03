<script setup lang="ts">
const skills = ['Empathy', 'Collaboration', 'Teamwork', 'Communication', 'Leadership', 'Problem Solving', 'Critical & Analytical Thinking', 'Positivity', 'Time Management', 'Client Management', 'Customer Service', 'Reading Documentation', 'Listening']
const traits = ['Curious', 'Assiduous', 'Proactive', 'Self-sufficient', 'Passionate', 'Patient', 'Diligent', 'Flexible', 'Confident', 'Humble', 'Helpful', 'Adaptable', 'Strives for Excellence']
</script>

<template>
  <Marquee class="mt-4 text-[color:#AD84C6] opacity-25" sm="mt-8" :array="skills" :reverse="false" />
  <Marquee class="mt-4 text-[color:#8784C7] opacity-25" :array="traits" :reverse="true" />
</template>

<style scoped>

</style>
