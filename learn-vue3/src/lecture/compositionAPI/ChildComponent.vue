<template>
  <div class="child">
    <h1>I'm Child Component</h1>
    <h2>Parent - props -> Child: {{ numArr }}</h2>
    <button @click="clickHandler">클릭</button>
  </div>
</template>

<script setup>
const { numArr } = defineProps({ numArr: Array });

const emit = defineEmits(['childNumArr']);

const clickHandler = () => {
  emit(
    'childNumArr',
    numArr.map((num) => num * 2),
  );
};
</script>

<style scoped>
.child {
  background-color: aquamarine;
  padding: 5px;
}
</style>
