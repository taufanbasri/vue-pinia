<template>
  <div>Ini Footer</div>

  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>
  <button @click="reset">Reset</button>

  <hr />
  <button @click="incrementWithActions">Increment With Actions</button>
  <button @click="decrementWithActions">Decrement With Actions</button>
  <button @click="incrementByWithActions(2)">Increment +2 with Actions</button>
</template>

<script setup>
import { useCounterStore } from "../stores/counter";

const counter = useCounterStore();

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
</script>
