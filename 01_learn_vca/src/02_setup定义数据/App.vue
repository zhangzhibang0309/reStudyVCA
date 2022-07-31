<template>
  <div>
    <h2>{{ message }}</h2>
  </div>

  <div>
    <button @click="changeAcount">点击更改</button>
    <p>{{ account.username }}</p>
    <p>{{ account.password }}</p>
  </div>
</template>

<script>
import { reactive } from "vue";

export default {
  setup() {
    // 1.定义普通的数据
    // 非响应式
    const message = "hello world";
    function changeMessage() {
      message = "hello";
      console.log(message);
    }

    // 2.定义响应式数据
    // 2.1reactive函数 定义复杂类型
    const account = reactive({
      username: "asd",
      password: "123",
    });
    function changeAcount() {
      account.username = "ewq";
      account.password = "321";
    }

    return {
      message,
      changeMessage,
      account,
      changeAcount,
    };
  },
};
</script>

<style></style>
