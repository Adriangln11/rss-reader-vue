<script setup>
import { ref } from 'vue'
import { useFeedStore } from '@/stores/feed'

const url = ref('')
const store = useFeedStore()
const handleSubmit = () => {
  if (url.value) {
    store.registerSource(url.value)
  }
}
</script>

<template>
  <div class="header">
    <form action="/" @submit.prevent="handleSubmit">
      <input type="url" required v-model="url" />
      <button type="submit">Add Source</button>
    </form>
  </div>
</template>
