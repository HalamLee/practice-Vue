<template>
  <div>
    <div :style="styleObject">
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ea quisquam, eos tenetur amet harum
      animi et cum debitis veritatis minima minus temporibus ratione nam tempora cupiditate aliquam
      nihil officiis ducimus.
    </div>
    <button @click="fontSize++">+</button>
    <button @click="fontSize--">-</button>
  </div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
  setup() {
    // const styleObject = reactive({
    //   color: 'red',
    //   fontSize: '13px',
    // });

    const fontSize = ref(13);

    const styleObject = computed(() => {
      return {
        color: 'red',
        fontSize: fontSize.value + 'px',
      };
    });
    return {
      styleObject,
      fontSize,
    };
  },
};
</script>

<style lang="scss" scoped></style>
