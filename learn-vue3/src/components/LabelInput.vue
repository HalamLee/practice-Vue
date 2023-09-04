<template>
  <label>
    {{ label }}
    <!-- <input v-model="username" type="text" /> -->
    <!-- <input
      :value="props.modelValue"
      @input="(event) => emit('update:modelValue', event.target.value)"
      type="text"
    /> -->
    <input v-model="value" type="text" />
  </label>
</template>

<script setup>
import { computed } from 'vue';

const props = defineProps(['modelValue', 'label']);
const emit = defineEmits(['update:modelValue']);
const value = computed({
  get() {
    return props.modelValue;
  },
  set(value) {
    emit('update:modelValue', value);
  },
});
</script>

<style lang="scss" scoped></style>
