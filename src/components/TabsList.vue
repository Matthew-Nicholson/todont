<template>
  <q-tabs
    class="tabs"
    active-color="primary"
    indicator-color="primary"
  >
    <q-tab
      v-for="tab in tabs"
      :key="tab.name"
      :name="tab.name"
      :label="tab.label"
      @click="setActiveTab(tab.name)"
    />
  </q-tabs>
</template>

<script setup lang="ts">
import { defineProps, withDefaults, defineEmits } from "vue";
import { Tabs } from "./tabs";
withDefaults(
	defineProps<{
		tabs: { name: Tabs; label: string }[];
		activeTab?: Tabs;
	}>(),
	{
		activeTab: Tabs.ALL,
	},
);

const emit = defineEmits<{
	"tabsList:update:activeTab": [Tabs];
}>();

const setActiveTab = (tab: Tabs) => {
	emit("tabsList:update:activeTab", tab);
};
</script>
