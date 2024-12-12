<template>
  <div class="todo-list">
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        {{ todo.text }}
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
defineProps<{
	todos: { id: number; text: string }[];
}>();
</script>
