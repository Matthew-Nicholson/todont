<template>
  <q-item
    clickable
    tag="div"
    class="todo-item"
  >
    <q-item-section
      v-if="completed"
      avatar
    >
      <q-icon name="check" />
    </q-item-section>

    <q-item-section>
      <q-item-label>{{ text }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script setup lang="ts">
import { defineProps, withDefaults } from "vue";

withDefaults(
	defineProps<{
		text?: string;
		subtext?: string;
		completed?: boolean;
		deleted?: boolean;
	}>(),
	{
		text: "",
		subtext: "",
		completed: false,
		deleted: false,
	},
);
</script>

<style scoped>

</style>
