<template>
  <div>
    <Header />
    <RouterView />
  </div>
</template>

<script setup>
import { RouterView } from 'vue-router'
import Header from './components/Header.vue';
import { onMounted } from 'vue';
import { useReviewsStore } from './stores/reviews';

const store = useReviewsStore()

onMounted(() => {
  store.fetchReviews()
})
</script>