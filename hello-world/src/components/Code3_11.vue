<script>
import { reactive } from 'vue';

export default {
  setup() {
    const items = reactive(['1번 아이템', '2번 아이템', '3번 아이템']);
    return {
      items,
    };
  },
};
</script>

<template>
  <div style="width: 200px">
    <ol>
      <li v-for="item in items" :key="item">{{ `${item}` }}</li>
    </ol>
  </div>
</template>
