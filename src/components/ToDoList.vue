
<script setup>
    //配列の受け取り
    const props = defineProps({
    todos: Array,
    });
</script>

<template>
    <!--タスク名と作成時刻を表示-->
    <div v-for="todo in todos" v-bind:key="todo.id">
        <h3>
            {{ todo.todoName }}
        </h3>
        <p> {{ todo.createdAt }}</p>

    </div>
</template>