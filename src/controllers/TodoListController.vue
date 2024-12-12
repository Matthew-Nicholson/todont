<template>
  <todo-list
  :todos="todos"
  />
</template>

<script setup lang="ts">
import { onMounted, onUnmounted, ref } from "vue";
import TodoList from "../views/TodoList.vue";

const todos = ref([]);

const loadTodos = () => {
	const todosFromStorage = localStorage.getItem("todos");
	todos.value = todosFromStorage ? JSON.parse(todosFromStorage) : [];
};

onMounted(() => {
	loadTodos();
	window.addEventListener("storage", syncStorage);
});

function syncStorage() {
	loadTodos();
}

onUnmounted(() => {
	window.removeEventListener("storage", syncStorage);
});
</script>
