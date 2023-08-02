<script setup lang="ts">
import { ref } from 'vue'

const message = ref('Hello World!')
const test: number = 1;
</script>

<template>
  <h1>{{ message }}</h1>
  <div>{{ test }}</div>
</template>