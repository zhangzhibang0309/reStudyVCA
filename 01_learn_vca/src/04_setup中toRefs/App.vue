<script>
import { reactive, toRef, toRefs } from "vue";

export default {
  setup() {
    const info = reactive({
      name: "zz",
      age: 22,
      height: "1.8",
    });

    // toRef toRefs
    // 将解构出来的值也包裹为响应式
    const { name, age } = toRefs(info);
    const height = toRef(info, "height");

    // ref相关的其他api
    /**
     * unref 语法糖：val = isRef(val) ? val.value : val
     * isRef 见名知意义
     * shallowRef  浅层
     * triggerRef 手动触发shallowRef -- triggerRef(info)
     */

    return {
      info,
      name,
      age,
      height,
    };
  },
};
</script>

<template>
  <div>
    <h2>info:{{ name }} - {{ age }} - {{ height }}</h2>
    <button @click="name = 'kobe'">修改name</button>
    <button @click="age++">修改age</button>
    <button @click="height = '1.88'">修改和height</button>
  </div>
</template>
