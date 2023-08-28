<template>
  <div>
    <button @click="increment">Click {{ state.count }}</button>
  </div>
</template>

<script>
import { reactive } from 'vue';

export default {
  setup() {
    const state = reactive({
      count: 0,
    });
    const increment = () => {
      state.count++;
    };
    return {
      state,
      increment,
    };
  },
};
</script>

<style lang="scss" scoped></style>
