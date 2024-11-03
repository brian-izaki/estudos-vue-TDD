<script lang="ts" setup>
import { DEFEAT_MESSAGE, VICTORY_MESSAGE } from '@/settings'
import { ref } from 'vue'

defineProps<{
  wordOfTheDay: string
}>()

const guessInProgress = ref('')
const guessSubmited = ref('')
</script>

<template>
  <input
    v-model="guessInProgress"
    type="text"
    @keydown.enter="guessSubmited = guessInProgress"
  />

  <p v-if="guessInProgress.length > 0">
    {{ guessSubmited === wordOfTheDay ? VICTORY_MESSAGE : DEFEAT_MESSAGE }}
  </p>
</template>
