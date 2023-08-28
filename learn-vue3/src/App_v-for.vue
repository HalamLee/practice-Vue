<template>
  <div>
    <h2>v-for</h2>
    <ul>
      <li v-for="(item, index) in items" :key="item.id">
        index: {{ index }}, message: {{ item.message }}
      </li>
    </ul>
    <hr />
    <h2>template v-for + v-if</h2>
    <ul>
      <template v-for="(item, index) in items" :key="item.id">
        <li v-if="item.id % 2">
          ID: {{ item.id }}, index: {{ index }}, message: {{ item.message }}
        </li>
      </template>
    </ul>
    <hr />
    <h2>template v-for + computed</h2>
    <template v-for="(item, index) in evenItems" :key="item.id">
      <li>ID: {{ item.id }}, index: {{ index }}, message: {{ item.message }}</li>
    </template>
    <hr />
    <h2>v-for + object</h2>
    <ul>
      <li v-for="(value, key, index) in myObject" :key="key">
        index: {{ index }}, key: {{ key }}, value: {{ value }}
      </li>
    </ul>
  </div>
</template>

<script>
import { computed, reactive } from 'vue';

export default {
  setup() {
    const items = reactive([
      { id: 1, message: 'Java' },
      { id: 2, message: 'HTML' },
      { id: 3, message: 'CSS' },
      { id: 4, message: 'JavaScript' },
    ]);

    const evenItems = computed(() => items.filter((item) => item.id % 2 === 0));

    const myObject = reactive({
      title: '제목',
      author: '홍길동',
      publishedAt: '2016-01-01',
    });
    return { items, evenItems, myObject };
  },
};
</script>

<style lang="scss" scoped></style>
