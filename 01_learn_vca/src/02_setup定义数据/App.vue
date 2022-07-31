<template>
  <div>
    <h2>{{ message }}</h2>
  </div>
  <hr />

  <div>
    <button @click="changeAcount">点击更改</button>
    <p>{{ account.username }}</p>
    <p>{{ account.password }}</p>
  </div>
  <hr />

  <div>
    <p>当前计数:{{ counter }}</p>
    <button @click="increment">+</button>
    <button @click="counter--">-</button>
  </div>
  <hr />

  <div>
    <!-- 浅层解包使用不需要.value -->
    <p>当前计数:{{ info.counter }}</p>
    <!-- 深层解包修改需要.value -->
    <button @click="info.counter.value++">+1</button>
  </div>
</template>

<script>
import { reactive } from "vue";
import { ref } from "vue";

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
    // 2.2ref函数：主要是简单类型
    // counter定义响应式数据
    const counter = ref(0);
    function increment() {
      counter.value++;
    }
    function decrement() {
      counter.value--;
    }

    // 3.ref在模板中自动解包是浅层解包
    const info = {
      counter,
    };

    return {
      message,
      changeMessage,
      account,
      changeAcount,
      counter,
      increment,
      decrement,
      info,
    };
  },
};
</script>

<style></style>
