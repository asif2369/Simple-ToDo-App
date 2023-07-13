<script setup>
import { ref } from "vue";

const taskName = ref("");
const taskArray = ref([]);

const addTaskToArray = () => {
    if (taskName.value) {
        taskArray.value.unshift(taskName.value);
    }
    taskName.value = "";
};

const removeTasks = (taskName) => {
    taskArray.value = taskArray.value.filter((t) => t != taskName);
};
</script>

<template>
    <main>
        <h1>Simple ToDo App</h1>
        <p class="sub-heading">(with simple animation)</p>
        <input
            v-model="taskName"
            type="text"
            placeholder="Enter task name..."
            @keypress.enter="addTaskToArray"
        />
        <TransitionGroup name="todoList">
            <li
                v-for="task in taskArray"
                :key="task"
                @click="removeTasks(task)"
            >
                {{ task }}
            </li>
        </TransitionGroup>
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
    position: relative;
}

h1 {
    font-size: 2rem;
    text-align: center;
    font-weight: bold;
}

.sub-heading {
    margin-bottom: 30px;
}

li {
    list-style: none;
    font-size: 1.5rem;
    border-radius: 12px;
    margin-top: 20px;
    padding: 10px 20px;
    box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.12);
    text-align: center;
    cursor: pointer;
    width: 100%;
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

/* animations */

.todoList-enter-from {
    opacity: 0;
    transform: scale(0.5);
}

.todoList-enter-to {
    opacity: 1;
    transform: scale(1);
}
.todoList-enter-active {
    transition: all 0.5s ease;
}
.todoList-leave-from {
    opacity: 1;
    transform: scale(1);
}

.todoList-leave-to {
    opacity: 0;
    transform: scale(0);
}
.todoList-leave-active {
    transition: all 0.5s ease;
    position: absolute;
}
.todoList-move {
    transition: all 0.5s ease;
}
</style>
