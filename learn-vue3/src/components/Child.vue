<template>
  <div class="card">
    <div class="card-header">Child Component</div>
    <div class="card-body">
      <p>{{ appMessage }}</p>
      <DeepChild />
    </div>
  </div>
</template>

<script setup>
import { inject } from 'vue';
import DeepChild from './DeepChild.vue';

const appMessage = inject('app-message');
</script>

<style lang="scss" scoped></style>
