<script setup lang="ts">
import priceValues from '@/assets/prices.json'

</script>

<template>
  <main class="grid">
    <div class="introduction">
      <p>
        Welcome to Steve Fletcher's driving school! We are dedicated to providing you with the best driving lessons and
        courses that
        will help you become a safe and confident driver. Our experienced instructors will guide you through every step
        of the way, ensuring that you learn all the necessary skills and techniques to pass your driving test with flying
        colours.
      </p>

      <p>
        Based in beautiful Norfolk we offer a range of residential and non-residential driving courses. We are just 90
        minutes away from London and easily accessible
        from most parts of the country.
      </p>
      <p>
        Steve Fletcher offers expert tuition with over 30 years of experience, and will teach you to drive in a friendly
        and
        relaxing manner.
      </p>
      <p>
        An intensive driving course is a great way to learn and really accelerate your driving ability.
      </p>
      <p>
        Learning to drive can be an expensive business, but surely it shouldn't just be about how cheap you can get your
        driving tuition. Cheapest doesn't mean best.
      </p>
      <p>
        If you are serious about passing your driving test and getting your full licence you want the best.
        There are always going to be driving schools that will undercut each other to try and get the edge on their
        competitors.
      </p>
      <p>
        We are not the cheapest, but we believe that we offer exceptional value for
        money.
      </p>
      <p>
        We are a small family run business offering patient and friendly instructors, with the emphasis on giving
        personally
        tailored tuition
        to each individual pupil.
      </p>
      <p>
        All Intensive courses are conducted on a strictly one to one basis (No car sharing) From past experience we know
        it's better this way.
        We have been specialising in intensive courses over the past 30 years, in which time we have helped several
        thousand
        learner drivers become qualified.
        You too could be joining these very soon.
      </p>
    </div>

    <article class="pricing-article">
      <h2>Pricing</h2>

      <ul>
        <li v-for="priceValue in priceValues" :key="priceValue.name">
          {{ priceValue.name }} - £{{ priceValue.price }}
        </li>
      </ul>
    </article>
  </main>
</template>

<style scoped>
p {
  margin-bottom: 1.5rem;
}

.grid {
  display: flex;
  flex-direction: column;
}

@media (min-width: 1024px) {
  .grid {
    display: grid;
    grid-template-columns: 2fr 1fr;
  }
}
</style>
