<template>
  <stupid-quote :quote="quote!"/>
</template>

<script setup lang="ts">
import StupidQuote from "src/views/StupidQuote.vue";
import { stupidQuotes } from "../data/stupidQuotes";

const quote = stupidQuotes[Math.floor(Math.random() * stupidQuotes.length)];
</script>
