<template>
  <div class="card mt-4">
    <div class="card-body">Lifecycle Child</div>
    <input id="input" type="text" />
  </div>
</template>

<script setup>
import { onBeforeMount, onBeforeUnmount, onMounted, onUnmounted } from 'vue';

// console.log('[Child] setup');

onBeforeMount(() => {
  console.log('[Child] onBeforeMount');
});

onMounted(() => {
  console.log('[Child] onMounted');
});

onBeforeUnmount(() => {
  console.log('[Child] onBeforeUnmount');
  console.log(document.querySelector('#input'));
});

onUnmounted(() => {
  console.log('[Child] onUnmounted');
  console.log(document.querySelector('#input'));
});
</script>

<style lang="scss" scoped></style>
