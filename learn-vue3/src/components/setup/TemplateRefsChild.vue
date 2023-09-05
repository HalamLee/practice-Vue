<template>
  <div>{{ $parent }}</div>
</template>

<script setup>
import { ref } from 'vue';

const message = ref('Hellooooo');
const sayHello = () => {
  alert(message.value);
};
defineExpose({ message, sayHello });
</script>

<style lang="scss" scoped></style>
