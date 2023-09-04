<template>
  <label>
    {{ label }}
    <input v-model="value" type="text" />
  </label>
</template>

<script setup>
import { computed } from 'vue';

const props = defineProps(['title', 'label']);
const emit = defineEmits(['update:title']);
const value = computed({
  get() {
    return props.title;
  },
  set(value) {
    emit('update:title', value);
  },
});
</script>

<style lang="scss" scoped></style>
