<template>
  <div>
    <h2>input value</h2>
    <!-- <input type="text" v-model="inputValue" /> -->
    <!-- <input type="text" v-model.lazy="inputValue" /> -->
    <!-- <input type="text" v-model.number="inputValue" /> -->
    <input type="text" v-model.trim="inputValue" />
    <div>{{ inputValue }}</div>
    <div>{{ typeof inputValue }}</div>

    <hr />
    <h2>textarea value</h2>
    <textarea v-model="textareaValue" />
    <div>{{ textareaValue }}</div>

    <hr />
    <h2>checkbox value</h2>
    <input
      type="checkbox"
      id="checkbox"
      v-model="checkboxValue"
      true-value="Yes"
      false-value="No"
    />
    <label for="checkbox">{{ checkboxValue }}</label>

    <hr />
    <h2>checkbox values</h2>
    <label for="html">
      <input type="checkbox" value="html" id="html" v-model="checkboxValues" />
      HTML
    </label>
    <label for="css">
      <input type="checkbox" value="css" id="css" v-model="checkboxValues" />
      CSS
    </label>
    <label for="javascript">
      <input type="checkbox" value="javascript" id="javascript" v-model="checkboxValues" />
      JavaScript
    </label>
    <div>{{ checkboxValues }}</div>

    <hr />
    <h2>radio value</h2>
    <label for="O">
      <input type="radio" name="type" id="O" value="O" v-model="radioValue" />
      O형
    </label>
    <label for="A">
      <input type="radio" name="type" id="A" value="A" v-model="radioValue" />
      A형
    </label>
    <div>{{ radioValue }}</div>

    <hr />
    <h2>select value</h2>
    <select v-model="selectValue">
      <option value="html">HTML 수업</option>
      <option value="css">CSS 수업</option>
      <option value="javascript">JavaScript 수업</option>
    </select>
    <div>{{ selectValue }}</div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const inputValue = ref('');
    const textareaValue = ref('');
    const checkboxValue = ref('Yes');
    const checkboxValues = ref([]);
    const radioValue = ref('O');
    const selectValue = ref('html');

    return { inputValue, textareaValue, checkboxValue, checkboxValues, radioValue, selectValue };
  },
};
</script>

<style lang="scss" scoped></style>
