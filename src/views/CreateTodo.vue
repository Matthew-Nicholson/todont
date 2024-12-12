<template>
  <div class="wrapper">
    <q-input outlined v-model="todoinput" label="What don't you want to accomplish today?" />
    <q-btn class="submit" color="primary" label="Create Todont" @click="createTodo" />
  </div>
</template>

<script setup lang="ts">
import { defineEmits, ref } from "vue";

const emit = defineEmits<{
	todoCreated: [string];
}>();

const todoinput = ref<string>("");

const createTodo = () => {
	emit("todoCreated", todoinput.value);
};
</script>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  padding: 1rem;
  margin: 1rem;
  gap: 1rem;
  border-radius: 1rem;
  background-color: #fff;
}

.submit {
  margin-top: auto;
}
</style>
