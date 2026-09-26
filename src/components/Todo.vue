<script setup>
// I don't know if I should be using "setup" attribute
import TodoCreate from './TodoCreate.vue';
import TodoItem from './TodoItem.vue';

</script>

<template>
    <div id="todo">
        <h1>To-do</h1>
        <TodoCreate />
        <div id="todo-list">
            <TodoItem />
            <TodoItem />
        </div>
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
    margin-top: 0.5rem;
    gap: 8px;
}
</style>