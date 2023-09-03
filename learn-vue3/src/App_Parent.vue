<template>
  <div class="parent">
    <h1>I'm Parent Component</h1>
    <ChildComponent :num-arr="[1, 2, 3]" @child-num-arr="handleChildNumArr" />
    <h2>Child - emit -> Parent: {{ numArr }}</h2>
  </div>
</template>

<script setup>
import ChildComponent from './ChildComponent.vue';
import { ref } from 'vue';

const numArr = ref([]);
const handleChildNumArr = (changedNumArr) => {
  numArr.value = changedNumArr;
};
</script>

<style scoped>
.parent {
  background-color: rgb(226, 187, 44);
  padding: 20px;
}
</style>
