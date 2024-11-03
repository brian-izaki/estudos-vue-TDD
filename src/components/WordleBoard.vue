<script lang="ts" setup>
import { DEFEAT_MESSAGE, VICTORY_MESSAGE } from '@/settings'
import englishWords from '@/assets/data/englishWordsWith5Letters.json'
import { ref } from 'vue'

defineProps({
  wordOfTheDay: {
    type: String,
    validator: (wordIncoming: string) => englishWords.includes(wordIncoming),
  },
})

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
