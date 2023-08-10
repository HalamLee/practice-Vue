<!-- ref와 reactive를 이용한 카운터 -->

<!-- ref -->
<!-- <script setup>
import { ref } from 'vue';

const refCounter = ref(0);

const refAddHandler = () => {
  refCounter.value++;
};

const refMinusHandler = () => {
  refCounter.value--;
};
</script>

<template>
  <h1>{{ refCounter }}</h1>
  <button type="button" @click="refAddHandler">plus</button>
  <button type="button" @click="refMinusHandler">minus</button>
</template> -->

<!-- reactive -->

<script setup>
import { reactive } from 'vue';

const counter = reactive({
  count: 0,
});

const reactiveAddHandler = () => {
  counter.count++;
};

const reactiveMinusHandler = () => {
  counter.count--;
};
</script>

<template>
  <h1>{{ counter.count }}</h1>
  <button type="button" @click="reactiveAddHandler">plus</button>
  <button type="button" @click="reactiveMinusHandler">minus</button>
</template>
