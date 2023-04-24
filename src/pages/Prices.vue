<script setup lang="ts">
import priceValues from '@/assets/prices.json'
import imgCardsUrl from '@/assets/images/cards.jpg'
</script>

<template>
  <main>

    <article v-for="priceValue in priceValues" :key="priceValue.name" class="price-article">
      <img class="price-image" :src="priceValue.image" />
      <div class="price-text-container">
        <p class="price-name">{{ priceValue.name }}</p>
        <p class="price-description">{{ priceValue.description }}</p>
        <p class="price-price">£{{ priceValue.price }}</p>
      </div>
    </article>

    <div class="card-information">
      <p>We accept most major credit/debit cards.</p>
      <img :src="imgCardsUrl" alt="credit cards">
      <p><i>Credit card payments will incur a 2% processing fee, there is no fee for using a debit card.</i></p>
    </div>
  </main>
</template>

<style scoped>
.price-article {
  margin-bottom: 4rem;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.price-text-container {
  padding: 0 2rem;
}

.price-name {
  font-weight: 800;
  font-size: 1.25rem;
}

.price-price {
  font-weight: 800;
  color: green;
}

.price-image {
  display: block;
  max-width: 220px;
  width:100%;
  height:100%;
  object-fit: cover;
  overflow: hidden;
}

.card-information {
  text-align: center;
}
</style>
