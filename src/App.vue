
<script setup>

import ToDoList from './components/ToDoList.vue';
import Header from './components/Header.vue';
import addButton from './components/addButton.vue';
import { reactive } from "@vue/reactivity";
const items = reactive([
  {
    id: 0,
    todoName: "勉強する",
    createdAt: "2021年12月30日",
    cleared: false,
  },

  {id: 1,
   todoName: "掃除する",
   createdAt: "2021年12月31日",
   cleared: false,
   },

]);

function appAction(newTodo) {
  items.push(newTodo)
  console.log(newTodo)
}

</script>

<template>
  <div class="container">
    <Header title="ToDo List" />
    <ToDoList :todos="items" />
    <addButton msg="追加" @add-todo="appAction"/>
  </div>
</template>