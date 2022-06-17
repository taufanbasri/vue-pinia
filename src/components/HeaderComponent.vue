<template>
  <div>Ini Header</div>
  <pre>Nilai state: {{ counter }}</pre>
  <pre>Nilai Getters: {{ getCount }}</pre>
  <pre>Nilai Getters: {{ doubleCount }}</pre>
  <pre>Nilai Getters dibagi dua: {{ dividedByTwo }}</pre>
  <pre>pokemon : {{ pokemon }}</pre>
</template>

<script setup>
import { computed } from "vue";
import { useCounterStore } from "../stores/counter";
import { usePokemonStore } from "../stores/pokemon";

const counterStore = useCounterStore();
const pokemonStore = usePokemonStore();

const counter = computed(() => counterStore.count);
const getCount = computed(() => counterStore.getCount);
const doubleCount = computed(() => counterStore.doubleCount);
const dividedByTwo = computed(() => counterStore.dividedBy(2));

const pokemon = computed(() => pokemonStore.pokemonDetails)

/**
 * Sama dengan fitur watch, tapi ini milik store
 */
counterStore.$subscribe((mutation, state) => {
  console.log(mutation, state);
});
</script>
