<script setup>
import TodoCreate from './TodoCreate.vue';
import TodoItem from './TodoItem.vue';

import { reactive } from 'vue';

const tasks = reactive([]);

function createTask(text) {
    tasks.push({ text: text, checked: false });
}

function deleteTask(id) {
    const taskIndex = tasks.findIndex(v => v.id === id);
    if (taskIndex !== -1) {
        tasks.splice(taskIndex, 1);
    }
}
</script>

<template>
    <div id="todo">
        <h1>To-do</h1>
        <TodoCreate @createTask="createTask" />
        <ul id="todo-list" v-for="(_, index) in tasks">
            <TodoItem v-model="tasks[index]" @deleteTask="tasks.splice(index, 1)" />
        </ul>
    </div>
</template>

<style scoped>
h1 {
    margin: 0;
    margin-bottom: 0.3em;
    font-size: 1.6rem;
    text-decoration: underline solid var(--border-colour);
    text-underline-offset: 5px;
}

#todo {
    background-color: var(--todo-colour);
    border: 1px solid var(--dark-border-colour);
    border-radius: 10px;
    width: clamp(300px, 24vw, 480px);
    padding: 0.5rem;
}

#todo-list {
    display: flex;
    flex-direction: column;
    margin: 0;
    margin-top: 0.5rem;
    gap: 8px;
    list-style: none;
    padding: 0;
}
</style>