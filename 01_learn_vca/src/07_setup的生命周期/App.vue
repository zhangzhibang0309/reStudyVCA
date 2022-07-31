<script>
import { onMounted } from "vue";

export default {
  setup() {
    // 可以注册多个
    // 删掉了created 和 beforeCreated 直接写在setup即可
    // 其他的钩子这里省略
    onMounted(() => {
      console.log("onMounted");
    });
    onMounted(() => {
      console.log("onMounted");
    });
    onMounted(() => {
      console.log("onMounted");
    });
  },
};
</script>

<template></template>
