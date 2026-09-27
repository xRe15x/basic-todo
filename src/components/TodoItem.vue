<script setup lang="ts">
import TodoItemButton from './TodoItemButton.vue';
import TodoItemCheckmark from './TodoItemCheckmark.vue';

import { ref, useTemplateRef } from "vue";

const model = defineModel({
    type: Object,
    default: { text: "", checked: false }
});

const emit = defineEmits(["deleteTask"])

let editing = ref(false);
const input = useTemplateRef("input");

function edit() {
    if (editing.value == false) {
        editing.value = true;
        input.value?.focus();
    } else { // Already editing, stop editing
        editing.value = false;
    }
}

</script>

<template>
    <div class="todo-item">
        <TodoItemCheckmark v-model="model.checked" />
        <input type="text" class="task-text" v-model="model.text" :readonly="!editing" ref="input"
            @keydown.enter="edit"></input>

        <TodoItemButton @click="edit">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
                <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
                <g id="SVGRepo_iconCarrier">
                    <path
                        d="M21.2799 6.40005L11.7399 15.94C10.7899 16.89 7.96987 17.33 7.33987 16.7C6.70987 16.07 7.13987
                        13.25 8.08987 12.3L17.6399 2.75002C17.8754 2.49308 18.1605 2.28654 18.4781 2.14284C18.7956 1.99914
                        19.139 1.92124 19.4875 1.9139C19.8359 1.90657 20.1823 1.96991 20.5056 2.10012C20.8289 2.23033 21.1225
                        2.42473 21.3686 2.67153C21.6147 2.91833 21.8083 3.21243 21.9376 3.53609C22.0669 3.85976 22.1294 4.20626
                        22.1211 4.55471C22.1128 4.90316 22.0339 5.24635 21.8894 5.5635C21.7448 5.88065 21.5375 6.16524 21.2799 6.40005V6.40005Z"
                        stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
                    <path d="M11 4H6C4.93913 4 3.92178 4.42142 3.17163 5.17157C2.42149 5.92172 2 6.93913 2 8V18C2 19.0609
                        2.42149 20.0783 3.17163 20.8284C3.92178 21.5786 4.93913 22 6 22H17C19.21 22 20 20.2 20 18V13"
                        stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
                </g>
            </svg>
        </TodoItemButton>

        <TodoItemButton @click="emit('deleteTask')">
            <svg fill="currentColor" viewBox="0 0 32 32" xmlns="http://www.w3.org/2000/svg" stroke="currentColor"
                stroke-width="0.00032">
                <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
                <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
                <g id="SVGRepo_iconCarrier">
                    <path d="M18.8,16l5.5-5.5c0.8-0.8,0.8-2,0-2.8l0,0C24,7.3,23.5,7,23,7c-0.5,0-1,0.2-1.4,0.6L16,
                        13.2l-5.5-5.5 c-0.8-0.8-2.1-0.8-2.8,0C7.3,8,7,8.5,7,9.1s0.2,1,0.6,1.4l5.5,5.5l-5.5,5.5C7.3,
                        21.9,7,22.4,7,23c0,0.5,0.2,1,0.6,1.4 C8,24.8,8.5,25,9,25c0.5,0,1-0.2,1.4-0.6l5.5-5.5l5.5,5.5c0.8,
                        0.8,2.1,0.8,2.8,0c0.8-0.8,0.8-2.1,0-2.8L18.8,16z" stroke="currentColor">
                    </path>
                </g>
            </svg>
        </TodoItemButton>
    </div>
</template>

<style scoped>
.todo-item {
    border: 1px solid var(--border-colour);
    display: flex;
    align-items: center;
    padding: 4px;
    gap: 3px;
    border-radius: 3px;
}

.task-text {
    flex: 1;
    background-color: transparent;
    border: none;
    font-size: 1rem;
}

.task-text:focus {
    outline: none;
}
</style>