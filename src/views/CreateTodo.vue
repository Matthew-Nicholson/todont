<template>
  <h1>CreateTodo</h1>
  <input type="text" v-model="label" />
  <input type="textarea" v-model="subtext" />
  <button @click="createTodo">Create Todo</button>
</template>

<script setup lang="ts">
import { defineEmits, ref } from "vue";

const emit = defineEmits<{
	todoCreated: [string, string];
}>();

const label = ref<string>("");
const subtext = ref<string>("");

const createTodo = () => {
	emit("todoCreated", label.value, subtext.value);
};
</script>
