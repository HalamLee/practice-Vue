<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ reverseMessage }}</p>
  </div>
</template>

<script setup>
import { ref, watch } from 'vue';

const message = ref('Hello Vue3');
const reverseMessage = ref('');

const reverseFunction = (newValue) => {
  console.log('즉시실행');
  reverseMessage.value = newValue.split('').reverse().join('');
};

watch(message, reverseFunction(message.value), {
  immediate: true,
});
</script>

<style lang="scss" scoped></style>
