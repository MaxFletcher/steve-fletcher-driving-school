<script setup lang="ts">
import { computed, ref, watchEffect } from 'vue';
import { useRoute } from 'vue-router';
import imgFbLogoUrl from '@/assets/images/f_logo_RGB-Blue_58.png';

const toggled = ref(false);
const navbarClasses = computed(() => toggled.value ? 'responsive' : '');

const route = useRoute();

</script>

<template>
  <header>
    <div class="header-container">
      <div>
        <h1>Steve Fletcher Driving School</h1>
        <div class="contact-details">
          <a href="mailto:aastevefletcher@hotmail.com">aastevefletcher@hotmail.com</a>
          <a href="tel:07887403480">07887403480</a>
        </div>
      </div>
      <div class="header-end">
        <a class="social-link" href="https://www.facebook.com/stevefletcherdrivingschool" target="_blank" rel="noopener noreferrer"><img class="fb-link" :src="imgFbLogoUrl" /></a>
      </div>
    </div>

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

.header-container {
  display: flex;
  justify-content: space-between;
  margin-bottom: 1rem;
}

li {
  list-style: none;
}

a {
  text-decoration: none;
}

h1 {
  padding: 0.25rem 2rem;
  color: darkgreen;
}

.navbar {
  overflow: hidden;
  background-color: #097530;
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

.contact-details {
  display: flex;
  flex-direction: column;
  padding-left: 2rem;
}

.contact-details a {
  color: #06402a;
  text-decoration: underline;
  background: none;
}

.contact-details a:hover {
  color: #47a782;
}

.header-end {
  display: flex;
  padding-right: 2rem;
}

.social-link {
  display: inline-block;
  align-self: flex-end;
}

.fb-link {
  width: 42px;
  height: 42px;
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
