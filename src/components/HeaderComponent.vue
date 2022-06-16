<template>
  <div>Ini Header</div>
  <pre>{{ counter }}</pre>
</template>

<script setup>
import { computed } from "vue";
import { useCounterStore } from "../stores/counter";

const counterStore = useCounterStore();
const counter = computed(() => counterStore.count);
</script>
