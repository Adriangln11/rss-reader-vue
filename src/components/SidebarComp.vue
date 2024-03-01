<script setup>
import { useFeedStore } from '@/stores/feed'

const store = useFeedStore()
const handleClick = (source) => {
  store.loadSource(source)
}
</script>

<template>
  <div class="sidebar">
    <div v-for="(source, index) in store.sources" :key="index">
      <a href="#" @click.prevent="() => handleClick(source)">{{ source.name }}</a>
    </div>
  </div>
</template>

<style scoped></style>
