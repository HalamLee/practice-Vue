<template>
  <main>
    <div class="container py-4">
      <MyButton @click="sayHello" />
      <FancyButton>
        <template #default="{ fancyMessage }">
          {{ fancyMessage }} Click!! <span style="color: red">@@@</span>
        </template>
      </FancyButton>
      <FancyButton />
      <FancyButton></FancyButton>
      <hr />
      <AppCard>
        <template #[slotArgs]="{ headerMessage }"> Hi {{ headerMessage }} </template>
        <template #default="{ childMessage, helloMessage }">
          {{ childMessage }}
          {{ helloMessage }}
        </template>
        <template #footer="{ footerMessage }">FFFFFooter {{ footerMessage }}</template>
      </AppCard>
      <hr />
      <AppCard>게시글입니다.</AppCard>
      <hr />
      <AppCard>
        <template #footer="{ footerMessage }">{{ footerMessage }}</template>
        게시글입니다.
      </AppCard>
    </div>
  </main>
</template>

<script setup>
import MyButton from './MyButton.vue';
import FancyButton from './FancyButton.vue';
import AppCard from './AppCard.vue';
import { ref } from 'vue';

const sayHello = () => alert('helloooo');
const slotArgs = ref('header');
</script>

<style lang="scss" scoped></style>
