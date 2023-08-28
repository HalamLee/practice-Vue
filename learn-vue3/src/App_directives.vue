<template>
  <div>
    <h2>v-text + v-html</h2>
    <p>{{ msg }}</p>
    <p v-text="msg" />
    <p v-html="htmlStr" />
    <p v-text="htmlStr" />
    <hr />
    <h2>v-once</h2>
    <p v-once>{{ msg }}!!!</p>
    <hr />
    <h2>v-memo</h2>
    <div v-memo="[subscribe, likes]">
      <p>subscribe: {{ subscribe }}</p>
      <p>views: {{ views }}</p>
      <p>likes: {{ likes }}</p>
    </div>
    <button @click="subscribe++">Subs++</button>
    <button @click="views++">Views++</button>
    <button @click="likes++">Likes++</button>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const msg = ref('안녕하세요');
    const htmlStr = ref('<strong>hello</strong>');

    const subscribe = ref(4000);
    const views = ref(400);
    const likes = ref(2);
    return { msg, htmlStr, subscribe, views, likes };
  },
};
</script>

<style lang="scss" scoped></style>
