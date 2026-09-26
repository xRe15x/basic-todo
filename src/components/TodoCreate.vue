<script setup></script>

<template>
    <form action="" id="create">
        <label for="item-name" id="item-name-label">Item name</label>
        <input type="text" name="item-name" id="item-name" placeholder="New task">
        <button type="submit" id="item-submit">Create</button>
    </form>
</template>

<style scoped>
#create {
    display: flex;
    height: 4vh;
    gap: 5px;
}

#item-name-label {
    display: none;
}

#item-name {
    flex: 1;
    background-color: transparent;
    border: 1px solid var(--border-colour);
    border-radius: 3px;
    font-size: 1.4rem;
    min-width: 0;
    box-sizing: border-box;
    padding: 0 0.3em;
}

#item-name:focus {
    outline: none;
}

#item-submit {
    flex: none;
    border: none;
    border-radius: 3px;
    background-color: var(--blue-colour);
    font-weight: bold;
    font-size: 1rem;
    padding: 0 0.5rem;
    cursor: pointer;
    transition: background-colour 0.5s;
}

#item-submit:hover {
    background-color: rgb(from var(--blue-colour) r g b / 0.8);
}

#item-submit:active {
    background-color: rgb(from var(--blue-colour) r g b / 0.6);
}
</style>