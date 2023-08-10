<script>
import { ref } from 'vue';

export default {
  // Composition API
  setup() {
    const abbr = ref('Hello');
    const normal = ref('World');
    return {
      abbr,
      normal,
    };
  },
};
</script>

<template>
  <p>줄임말과 원래말을 입력하세요.</p>
  <input type="text" v-bind:value="abbr" />
  <input type="text" v-model="normal" />
  <hr />
  <abbr v-bind:title="normal">{{ abbr }}</abbr>
</template>
