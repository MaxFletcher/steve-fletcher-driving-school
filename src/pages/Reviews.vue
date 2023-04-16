<script setup lang="ts">
import reviewValues from '@/assets/reviews.json';

</script>

<template>
  <main>
    <article v-for="reviewValue, i in reviewValues" :key="i" class="price-article">
      <p class="price-name">{{ reviewValue.reviewer }} - {{ reviewValue.reviewerLocation }}</p>
      <p class="price-price">{{ reviewValue.review }}</p>
    </article>
  </main>
</template>

<style scoped>
article {
  margin-bottom: 1.5rem;
}
</style>
