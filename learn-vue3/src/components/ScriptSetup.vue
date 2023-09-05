<template>
  <div class="container py-4">
    {{ msg }}
    <br />
    {{ message }}
    <input v-model="message" type="text" />
    <button @click="sayHello">click</button>
    <PostItem type="news" title="제목" contents="내용" :is-like="true" />
    <PostItem type="news" title="제목" contents="내용" :is-like="true" />
    <hr />
    <TemplateRefsChild ref="child" />
    <template v-if="child">{{ child.message }}</template>
    <hr />
    <MyButton class="parent-class" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import axios from 'axios';
import PostItem from './setup/PostItem.vue';
import TemplateRefsChild from './setup/TemplateRefsChild.vue';
import MyButton from './setup/MyButton.vue';

const msg = 'Hello World!';
const message = ref('hi');
const sayHello = () => {
  alert('Hello World!');
};
const child = ref(null);

defineExpose({ msg, sayHello });

const response = await axios('https://dummy.restapiexample.com/api/v1/employees');
console.log('response', response);
</script>

<style lang="scss" scoped></style>
