<script setup>
import { ref } from 'vue';
import { useTodosStore } from './stores/todos';
import { storeToRefs } from 'pinia';

const newTodo = ref('');

const todosStore = useTodosStore();

const { filteredTodos } = storeToRefs(todosStore);
const { addTodo, toggleTodo, updateFilter } = todosStore;

const addNewTodo = (text) => {
  addTodo(text);
  newTodo.value = '';
};
</script>

<template>
  <main>
    <div>
      <button @click="() => updateFilter('all')">all</button>
      <button @click="() => updateFilter('finished')">finished</button>
      <button @click="() => updateFilter('unfinished')">unfinished</button>
    </div>
    <input type="text" v-model="newTodo" />
    <button @click="() => addNewTodo(newTodo)">Add</button>
    <div v-for="todo in filteredTodos" style="display: flex">
      <h1 :style="todo.isFinished && { textDecoration: 'line-through' }">
        {{ todo.text }}
      </h1>
      <button @click="() => toggleTodo(todo.id)">toggle</button>
    </div>
  </main>
</template>
