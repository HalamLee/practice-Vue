<script setup>
import HelloWorld from './components/HelloWorld.vue';
import TheWelcome from '@components/TheWelcome.vue';
import Code38 from './components/Code3_8.vue';
import Counter from '@components/Counter.vue';
import Conditional from '@components/Conditional.vue';
import List from '@components/List.vue';
import Code3_11 from './components/Code3_11.vue';
import Code3_12 from './components/Code3_12.vue';
import Code3_13 from './components/Code3_13.vue';
</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <!-- <TheWelcome /> -->
    <!-- <Code38 /> -->
    <!-- <Counter /> -->
    <!-- <Conditional /> -->
    <!-- <List /> -->
    <!-- <Code3_11 /> -->
    <!-- <Code3_12 /> -->
    <Code3_13 />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
