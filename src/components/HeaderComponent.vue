<template>
  <div>Ini Header</div>
  <pre>{{ counter }}</pre>
</template>

<script setup>
import { computed } from "vue";
import { useCounterStore } from "../stores/counter";

const counterStore = useCounterStore();
const counter = computed(() => counterStore.count);

/**
 * Sama dengan fitur watch, tapi ini milik store
 */
counterStore.$subscribe((mutation, state) => {
  console.log(mutation, state);
});
</script>
