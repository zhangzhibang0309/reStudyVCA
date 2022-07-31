<template>
  <h2>{{ counter }}</h2>
  <button @click="increment">+</button>
  <button @click="decrement">-</button>
</template>

<script>
import useCounter from "./hooks/useCounter";

export default {
  setup() {
    return {
      ...useCounter(),
    };
  },
};
</script>

<style></style>
