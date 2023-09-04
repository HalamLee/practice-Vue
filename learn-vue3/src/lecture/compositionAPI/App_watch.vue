<template>
  <div><input type="text" v-model="message" /></div>
</template>

<script setup>
import { ref, watch } from 'vue';

const message = ref('');

watch(message, (newValue, oldValue) => {
  console.log('newValue: ', newValue);
  console.log('oldValue: ', oldValue);
});
</script>

<style scoped></style>
