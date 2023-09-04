<!-- <template>
  <div>
    <button class="btn btn-primary" @click="createPost()">button</button>
  </div>
</template>

<script setup>
const emit = defineEmits(['createPost']);

const createPost = () => {
  emit('createPost', 1, 2, 3, 4);
};
</script>

<style lang="scss" scoped></style> -->

<template>
  <div class="row g-3">
    <div class="col col-2">
      <select v-model="type" class="form-select" aria-label="Default select example">
        <option value="news">뉴스</option>
        <option value="notice">공지사항</option>
      </select>
    </div>
    <div class="col col-8">
      <input v-model="title" type="text" class="form-control" />
    </div>
    <div class="col col-2 d-grid">
      <button class="btn btn-primary" @click="createPost">추가</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// const emit = defineEmits(['createPost']);

// const createPost = () => {
//   emit('createPost', 1, 2, 3, 4);
// };

const type = ref('news');

const title = ref('');

const emit = defineEmits({
  createPost: (newPost) => {
    if (!newPost.type) {
      console.log('x');
      return false;
    } else if (!newPost.title) {
      return false;
    }
    return true;
  },
});

const createPost = () => {
  const newPost = {
    type: type.value,
    title: title.value,
  };
  emit('createPost', newPost);
  type.value = 'news';
  title.value = '';
};
</script>

<style lang="scss" scoped></style>
