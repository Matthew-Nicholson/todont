<template>
  <div class="layout">
    <div class="left">
      <stupid-quote-controller class="one-third"/>
      <create-todo-controller class="two-thirds"/>
    </div>
    <todo-list-controller class="right"/>
  </div>
</template>

<script setup lang="ts">
import CreateTodoController from "src/controllers/CreateTodoController.vue";
import StupidQuoteController from "src/controllers/StupidQuoteController.vue";
import TodoListController from "src/controllers/TodoListController.vue";
</script>

<style scoped>
.layout {
  display: flex;
  background-color: #f0f0f0;
  height: 100vh;
}

.left {
  flex: 2 1 33%;
  display: flex;
  flex-direction: column;
}

.one-third {
  flex: 1 1 33%;
}

.two-thirds {
  flex: 2 1 67%;
}

.right {
  flex: 1 1 67%;
}
</style>
