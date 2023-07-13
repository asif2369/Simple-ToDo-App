<script setup></script>

<template>
    <main>
        <input type="text" placeholder="Enter task name..." />
        <ul class="todo-list">
            <li>Task Name 1</li>
            <li>Task Name 2</li>
        </ul>
    </main>
</template>

<style scoped>
main {
    max-width: 600px;
    padding-top: 60px;
    padding-bottom: 60px;
    margin-left: auto;
    margin-right: auto;
    height: 100vh;
    text-align: center;
}

.todo-list {
    list-style: none;
    padding: 0;
    margin: 0;
    font-size: 1.5rem;
}

.todo-list li {
    border-radius: 12px;
    margin-top: 20px;
    padding: 10px 20px;
    box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.12);
    text-align: center;
    cursor: pointer;
}

input {
    font-size: 1.5rem;
    width: 100%;
    border-radius: 12px;
    border: 1px solid rgba(128, 128, 128, 0.13);
    padding: 20px;
    margin-bottom: 20px;
    box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.12);
}
</style>
