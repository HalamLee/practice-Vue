<template>
  <div>
    <div :class="{ active: isActive, 'text-danger': hasError }">텍스트입니다.</div>
    <button @click="toggle">toggle</button>
    <button @click="hasError = !hasError">toggle Error</button>
    <p v-if="isActive">😆 {{ isActive }}</p>
    <p v-else>😭 {{ isActive }}</p>
    <hr />
    <div :class="classObject">class Object</div>
    <div :class="[isActive && 'active', hasError && 'text-danger']">class Array</div>
  </div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
  setup() {
    const isActive = ref(true);
    const hasError = ref(false);

    // const classObject = reactive({
    //   active: isActive,
    //   'text-danger': hasError,
    // });

    const classObject = computed(() => {
      return {
        active: true && true,
        'text-danger': true && true,
      };
    });

    const toggle = () => {
      isActive.value = !isActive.value;
    };
    return { isActive, toggle, hasError, classObject };
  },
};
</script>

<style scoped>
.active {
  font-weight: 900;
}

.text-danger {
  color: red;
}
</style>
