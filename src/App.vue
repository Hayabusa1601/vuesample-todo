
<script setup>

import ToDoList from './components/ToDoList.vue';
import Header from './components/Header.vue';
import addButton from './components/addButton.vue';
import { reactive } from "vue";

//ToDoListに渡す本体
const items = reactive([
  {
    id: 0,
    todoName: "勉強する",
    createdAt: "2021年12月30日",
    cleared: false,
  },

  {
   id: 1,
   todoName: "掃除する",
   createdAt: "2021年12月31日",
   cleared: false,
   },

]);

//ToDoListの追加処理
function appAction(newTodo) {
  items.push(newTodo)
}

</script>

<template>
  <div class="container">
    <!--ヘッダー-->
    <Header title="ToDo List" />
    <!--ToDoListの呼び出し-->
    <ToDoList :todos="items" />
    <!--追加ボタンの呼び出し-->
    <addButton msg="追加" @add-todo="appAction"/>
  </div>
</template>