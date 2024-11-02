<script lang="ts" setup>
defineProps<{
  wordOfTheDay: string
}>()
</script>

<template>
  <input type="text" />
  <p>You won!</p>
  <p>{{ wordOfTheDay }}</p>
</template>
