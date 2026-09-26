<template>
    <input type="checkbox" class="checkmark">
</template>

<style scoped>
.checkmark {
    width: 30px;
    aspect-ratio: 1 / 1;
    margin: 0;
    cursor: pointer;
    appearance: none;
    border: 2px solid var(--border-colour);
    border-radius: 100%;
    overflow: hidden;
    position: relative;
    display: grid;
    place-items: center;
}

.checkmark:hover {
    border-color: rgb(from var(--lighter-blue-colour) r g b / 0.4);
}

.checkmark::before,
.checkmark::after {
    content: "";
    width: 100%;
    height: 100%;
    display: block;
    position: absolute;
    background-color: var(--blue-colour);
    opacity: 0;
    transition: opacity 0.2s;
}

.checkmark:after {
    background-color: var(--text-colour);
    clip-path: polygon(14% 44%, 0% 58%, 38% 95%, 100% 25%, 85% 10%, 38% 63%, 14% 44%);
    position: static;
    box-sizing: border-box;
    width: 60%;
    height: 60%;
}

.checkmark:checked::before,
.checkmark:checked::after {
    opacity: 1;
}
</style>