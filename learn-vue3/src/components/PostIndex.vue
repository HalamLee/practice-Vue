<template>
  <div>
    <main>
      <div class="container py-4">
        <PostCreate @create-post="createPost" />
        <hr class="my-4" />
        <div class="row g-3">
          <div v-for="post in posts" :key="post.id" class="col col-4">
            <!-- <AppCard
              :title="post.title"
              :contents="post.contents"
              :type="post.type"
              :is-like="post.isLike"
              /> -->
            <AppCard v-bind="post" @toggle-like="post.isLike = !post.isLike" />
          </div>
        </div>
        <hr class="my-4" />
        <!-- <LabelInput :model-value="username" @update:model-value="(value) => (username = value)" /> -->
        <LabelInput v-model="username" label="이름" />
      </div>
    </main>
  </div>
</template>

<script setup>
import AppCard from './AppCard.vue';
import PostCreate from './PostCreate.vue';
import LabelInput from './LabelInput.vue';

import { reactive, ref } from 'vue';

const posts = reactive([
  { id: 1, title: '제목1', contents: '내용1', isLike: true, type: 'news' },
  { id: 2, title: '제목2', contents: '내용2', isLike: true, type: 'news' },
  { id: 3, title: '제목3', contents: '내용3', isLike: true, type: 'news' },
  { id: 4, title: '제목4', contents: '내용4', isLike: true, type: 'news' },
  { id: 5, title: '제목5', contents: '내용5', isLike: false, type: 'notice' },
  { id: 6, title: '제목6', contents: '내용6', isLike: false, type: 'notice' },
]);

const createPost = (newPost) => {
  console.log('newPost: ', newPost);
  posts.push(newPost);
};

const username = ref('');
</script>

<style lang="scss" scoped></style>
