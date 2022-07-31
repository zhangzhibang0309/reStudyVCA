<template>
  <p>ShowInfo</p>
  <p>{{ name }}</p>
  <p>{{ age }}</p>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: "",
    },
    age: {
      type: Number,
      default: 0,
    },
  },
  setup() {},
};
</script>

<style></style>
