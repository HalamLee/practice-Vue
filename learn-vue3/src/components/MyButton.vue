<template>
  <div class="p-3 bg-danger">
    <button v-bind="$attrs" class="btn btn-primary" type="button">My Button</button>
  </div>
</template>

<script setup>
defineOptions({
  inheritAttrs: false,
});
</script>

<style lang="scss" scoped></style>
