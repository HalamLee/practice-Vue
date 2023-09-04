<template>
  <div>
    <LabelInput
      :model-value="firstname"
      @update:model-value="(value) => emit('update:firstname', value)"
      label="성"
    />
    <LabelInput
      :model-value="lastname"
      @update:model-value="(value) => emit('update:lastname', value)"
      label="이름"
    />
  </div>
</template>

<script setup>
import LabelInput from './LabelInput.vue';

const props = defineProps(['firstname', 'lastname']);
const emit = defineEmits(['update:firstname', 'update:lastname']);
</script>

<style lang="scss" scoped></style>
