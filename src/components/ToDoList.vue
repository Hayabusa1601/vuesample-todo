
<script setup>
    const props = defineProps({
    todos: Array,
    });
</script>

<template>
    <div v-for="todo in todos" v-bind:key="todo.id">
        <h3>
            {{ todo.todoName }}
        </h3>
        <p> {{ todo.createdAt }}</p>

    </div>
</template>