<template>
  <div>
    <form action="" @submit.prevent>
      <input v-model.lazy="title" type="text" placeholder="Title" />
      <br />
      <textarea v-model.lazy="contents" placeholder="Contents"></textarea>
      <hr />
      <button @click="save(title, contents)">저장</button>
    </form>
  </div>
</template>

<script setup>
import { ref, watchEffect } from 'vue';

const title = ref('');
const contents = ref('');

const save = (title, contents) => {
  console.log(`저장되었습니다. title: ${title}, contents: ${contents}`);
};

watchEffect(() => {
  console.log('watchEffect');
  save(title.value, contents.value);
  console.log(title.value);
  console.log(contents.value);
});
</script>

<style lang="scss" scoped></style>
