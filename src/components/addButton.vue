<script setup>
import { computed, ref } from "vue";
//リアクティブなaddTodoの作成
const addTodo = ref("");

//createdAtの作成
const now = new Date();
const y = now.getFullYear();
const m = now.getMonth() + 1;
const d = now.getDate();
const createdAt = y + '年' + m + '月' + d + '日';

//名前の受け取り
const props  = defineProps({
    msg:String,

});

//emit準備
const emit = defineEmits(['add-todo'])
//入力されているか確認
const isInput = computed(() => addTodo.value.length > 0);

//TodoListへの追加の本体
function submitTodo() {

    const newTodo = {
        id: Math.floor(Math.random() * 100000),
        todoName: addTodo.value,
        createdAt: createdAt,
        cleared: false,
    }
    console.log(newTodo)
    //add-todo関数にnewTodoとしてemit
    emit('add-todo', newTodo)

}
</script>

<template>
    <!--入力欄-->
    <input v-model="addTodo" />
    <!--入力されていれば押せる追加ボタン-->
    <button :disabled="!isInput" @click="submitTodo">
        {{ msg }}
    </button>
    
</template>