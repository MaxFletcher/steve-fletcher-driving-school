<script setup lang="ts">
import { computed, ref, watchEffect } from 'vue';
import { useRoute } from 'vue-router';

const toggled = ref(false);
const navbarClasses = computed(() => toggled.value ? 'responsive' : '');

const route = useRoute();

</script>

<template>
  <header>
    <h1>Steve Fletcher Driving School</h1>

    <nav class="navbar" :class="navbarClasses">
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/prices">Prices</RouterLink>
      <RouterLink to="/reviews">Reviews</RouterLink>
      <RouterLink to="/contact">Contact Us</RouterLink>
      <RouterLink to="/terms">Terms and conditions</RouterLink>
      <a class="icon" @click="$event => toggled = !toggled">
        &#9776;
      </a>
    </nav>
  </header>
</template>

<style scoped>
header {
  display: flex;
  flex-direction: column;
  background-color: lightgreen;
}

li {
  list-style: none;
}

a {
  text-decoration: none;
}

h1 {
  padding: 1rem 2rem;
  color: darkgreen;
}

.navbar {
  overflow: hidden;
  background-color: #097530;
  padding: 0 2rem;
}

.navbar a {
  float: left;
  display: block;
  color: #f2f2f2;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
}

.navbar a:hover {
  background-color: #ddd;
  color: black;
}

.navbar a.active {
  background-color: #04AA6D;
  color: white;
}

.navbar .icon {
  display: none;
}

@media screen and (max-width: 600px) {
  .navbar a:not(:first-child) {
    display: none;
  }

  .navbar a.icon {
    float: right;
    display: block;
  }
}

@media screen and (max-width: 600px) {
  .navbar.responsive {
    position: relative;
  }

  .navbar.responsive .icon {
    position: absolute;
    right: 0;
    top: 0;
  }

  .navbar.responsive a {
    float: none;
    display: block;
    text-align: left;
  }
}
</style>
