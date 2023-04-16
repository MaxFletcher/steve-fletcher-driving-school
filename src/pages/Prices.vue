<script setup lang="ts">
import priceValues from '@/assets/prices.json'
import imgCardsUrl from '@/assets/images/cards.jpg'

</script>

<template>
  <main>

    <article v-for="priceValue in priceValues" :key="priceValue.name" class="price-article">
      <p class="price-name">{{ priceValue.name }}</p>
      <p class="price-description">{{ priceValue.description }}</p>
      <p class="price-price">£{{ priceValue.price }}</p>
    </article>

    <p>We accept most major credit/debit cards.</p>
    <img :src="imgCardsUrl" alt="credit cards">
    <p><i>Credit card payments will incur a 2% processing fee, there is no fee for using a debit card.</i></p>
  </main>
</template>

<style scoped>
.price-article {
  margin-bottom: 1rem;
}

.price-name {
  font-weight: 800;
  font-size: 1.25rem;
}

.price-price {
  font-weight: 800;
  color: green;
}
</style>
