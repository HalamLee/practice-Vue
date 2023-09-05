<template>
  <div class="container py-4">
    <input ref="inputRef" value="hi~" type="text" />
    <hr />
    <button @click="visible = !visible">Toggle Child</button>
    <LifecycleChild v-if="visible" />
    <p id="message">{{ message }}</p>
  </div>
</template>

<script setup>
import { onBeforeMount, onBeforeUpdate, onMounted, onUpdated, ref } from 'vue';
import LifecycleChild from './LifecycleChild.vue';

const inputRef = ref(null);
const message = ref('');
const visible = ref(false);

// console.log('setup');

// onBeforeMount(() => {
//   console.log('onBeforeMount', inputRef.value);
// });

// onMounted(() => {
//   console.log('onMounted', inputRef.value.value);
// });

onBeforeUpdate(() => {
  console.log('onBeforeUpdate', message.value);
  console.log('DOM Content: ', document.querySelector('#message').textContent);
});

onUpdated(() => {
  console.log('onUpdated', message.value);
  console.log('DOM Content: ', document.querySelector('#message').textContent);
});
</script>

<style lang="scss" scoped></style>
