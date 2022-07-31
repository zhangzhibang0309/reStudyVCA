<template></template>

<script>
import { ConstantTypes } from "@vue/compiler-core";
import { reactive } from "vue";
import { ref } from "vue";

export default {
  setup() {
    // 定义响应式数据： reactive/ref
    // 强调：ref也可以定义复杂的数据
    const info = ref({});
    console.log(info.value);

    // 1.reactive的使用场景
    // 一般是一些本地的复杂数据，或者说是有关联的 比如有帐号密码才能登录
    const acount = reactive({
      username: "awd",
      password: 123,
    });

    // 2.ref的应用场景：其他的场景基本都用ref()
    // 2.1定义本地的一些简单数据
    const message = ref("Hello World");
    const counter = ref(0);

    // 2.2从网络中获取的一些数据
    const music = ref([]);
    onMounted(() => {
      const serverMusic = ["海阔天空", "小苹果", "one last kiss"];
      music.value = serverMusic;
    });
  },
};
</script>

<style></style>
