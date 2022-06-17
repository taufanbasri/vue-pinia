<template>
  <div>Ini Footer</div>

  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>
  <button @click="reset">Reset</button>

  <hr />
  <button @click="incrementWithActions">Increment With Actions</button>
  <button @click="decrementWithActions">Decrement With Actions</button>
  <button @click="incrementByWithActions(2)">Increment +2 with Actions</button>

  <hr />
  <button @click="fetchPokemon('ditto')">fetch pokemon ditto</button>
  <button @click="resetPokemon">reset pokemon</button>
</template>

<script setup>
import { useCounterStore } from "../stores/counter";
import { usePokemonStore } from "../stores/pokemon";

const counter = useCounterStore();
const pokemon = usePokemonStore();

const increment = () => {
  counter.$patch((state) => {
    state.count++;
  });
};

const decrement = () => {
  counter.$patch((state) => {
    state.count--;
  });
};

const reset = () => {
  counter.$reset(); /** ini fungsi bawaan pinia */
};

const incrementWithActions = () => {
  counter.increment();
};

const decrementWithActions = () => {
  counter.decrement();
};

const incrementByWithActions = (number) => {
  counter.incrementBy(number);
};

const fetchPokemon = (name) => {
  pokemon.getPokemonDetails(name);
};

const resetPokemon = () => pokemon.$reset()
</script>
