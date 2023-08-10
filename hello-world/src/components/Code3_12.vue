<script>
import { reactive, computed } from 'vue';

export default {
  setup() {
    const arr = reactive([
      { id: 1, text: '1번 아이템' },
      { id: 2, text: '2번 아이템' },
      { id: 3, text: '3번 아이템' },
      { id: 4, text: '4번 아이템' },
      { id: 5, text: '5번 아이템' },
    ]);

    const small_items = computed(() => {
      return arr.filter((i) => i.id < 3);
    });

    const big_items = computed(() => {
      return arr.filter((i) => i.id >= 3);
    });

    return {
      small_items,
      big_items,
    };
  },
};
</script>

<template>
  <h2>Small Items</h2>
  <p v-for="item in small_items" :key="item.id">{{ item.text }}</p>
  <h2>Bit Items</h2>
  <p v-for="item in big_items" :key="item.id">{{ item.text }}</p>
</template>
