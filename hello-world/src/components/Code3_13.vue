<script>
import { ref, watch, watchEffect } from 'vue';

export default {
  setup() {
    const count_1 = ref(0);
    const count_2 = ref(0);
    const state = ref('실행 중');

    watch(
      count_1,
      (cur, prev) => {
        console.log('Watch: ' + prev + ' ==> ' + cur);
      },
      {
        immediate: true,
      }
    );

    watch([count_1, count_2], (cur, prev) => {
      console.log('Multiple Watch : ' + prev + ' ==> ' + cur);
    });

    const stop = watchEffect(
      () => {
        console.log(
          `watchEffect Called => count1: ${count_1.value} count2: ${count_2.value}`
        );
      },
      {
        flush: 'post',
      }
    );

    const onStop = () => {
      state.value = '중지';
      stop();
    };

    return {
      count_1,
      count_2,
      state,
      onStop,
    };
  },
};
</script>

<template>
  <p>{{ count_1 }}</p>
  <button @click="count_1++">1st 카운트 증가</button>
  <p>{{ count_2 }}</p>
  <button @click="count_2++">2nd 카운트 증가</button>
  <p>상태: {{ state }}</p>
  <button @click="onStop()">watchEffect 중지</button>
</template>
