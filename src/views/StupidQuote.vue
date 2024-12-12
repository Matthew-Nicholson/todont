<template>
  <blockquote>{{ quote }}</blockquote>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
defineProps<{
	quote: string;
}>();
</script>

<style scoped>
blockquote {
  font-family: 'Georgia', serif; /* Elegant serif font */
  font-size: 1.5rem; /* Adjust font size */
  font-style: italic;
  color: #333; /* Dark gray text */
  background-color: #f9f9f9; /* Subtle light gray background */
  padding: 15px 20px; /* Padding inside the quote */
  margin: 20px auto; /* Space around the blockquote */
  max-width: 600px; /* Limit the width */
  line-height: 1.6; /* Improve readability */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* Add a subtle shadow */
  border-radius: 1rem;
  margin: 1rem;
}

blockquote::before {
  content: "“"; /* Add an opening quote */
  font-size: 3rem; /* Make it larger */
  color: #0078D7; /* Match border color */
  position: relative;
  top: 10px;
  left: -10px;
}

blockquote::after {
  content: "”"; /* Add a closing quote */
  font-size: 3rem;
  color: #0078D7;
  position: relative;
  top: 10px;
  right: -10px;
}

</style>
