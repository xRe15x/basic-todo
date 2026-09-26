<template>
    <button>
        <slot></slot>
    </button>
</template>

<style scoped>
button {
    padding: 0;
    border: 0;
    width: 26px;
    align-self: center;
    aspect-ratio: 1 / 1;
    background-color: transparent;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
}

button>* {
    width: 100%;
    height: 100%;
}
</style>