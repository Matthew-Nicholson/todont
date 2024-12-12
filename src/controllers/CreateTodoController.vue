<template>
<create-todo @todo-created="onTodoCreated"/>
</template>

<script setup lang="ts">
import CreateTodo from "../views/CreateTodo.vue";

const onTodoCreated = (todo: string) => {
	console.log(todo);
};
</script>
