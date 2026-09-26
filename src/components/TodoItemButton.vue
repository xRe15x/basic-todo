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


button :deep(path) {
    transition: color 0.15s;
}


button>:deep(svg) {
    width: 100%;
    height: 100%;
}

button:hover :deep(path) {
    color: var(--lighter-blue-colour);
}

button:active :deep(path) {
    color: rgb(from var(--lighter-blue-colour) r g b / 0.7);
}
</style>