<template>
  <create-todo @todo-created="onTodoCreated"/>
</template>

<script setup lang="ts">
import CreateTodo from "../views/CreateTodo.vue";

function onTodoCreated(todo: string) {
	const todosFromStorage = localStorage.getItem("todos");
	const todos = todosFromStorage ? JSON.parse(todosFromStorage) : [];
	const newTodos = [
		...todos,
		{
			id: Date.now(),
			text: todo,
		},
	];
	localStorage.setItem("todos", JSON.stringify(newTodos));
}
</script>
