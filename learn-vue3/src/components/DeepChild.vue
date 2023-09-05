<template>
  <div class="card">
    <div class="card-header">Deep Child Component</div>
    <div class="card-body">
      <p>{{ staticMessage }}</p>
      <p>{{ message }}</p>
      <p>{{ count }}</p>
      <p>{{ appMessage }}</p>
    </div>
  </div>
</template>

<script setup>
import { inject } from 'vue';

const staticMessage = inject('static-message', 'default message');
const { message, updateMessage } = inject('message');
updateMessage('!');
message.value = message.value + 'dfdhk';
const count = inject('count');

const appMessage = inject('app-message');
</script>

<style lang="scss" scoped></style>
