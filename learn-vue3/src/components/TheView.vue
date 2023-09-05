<template>
  <main>
    <div class="container py-4">
      <MyButton @click="sayHello" />
    </div>
  </main>
</template>

<script setup>
import MyButton from './MyButton.vue';

const sayHello = () => alert('helloooo');
</script>

<style lang="scss" scoped></style>
