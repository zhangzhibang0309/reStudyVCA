<template>
  <p>ShowInfo:{{ info }}</p>
  <!-- 代码没有错误，但是违背规范（单项数据流规范） -->
  <button @click="info.name = 'kobe'">修改名字（不规范）</button>
  <!-- 正确的做法：符合单项数据流规范，子组件不要修改父组件传过来的值 -->
  <button @click="showInfoBtnClick">修改名字</button>
</template>

<script>
export default {
  props: {
    info: {
      type: Object,
      default: () => ({}),
    },
  },
  emits: ["changeInfoName"],
  setup(props, context) {
    function showInfoBtnClick() {
      context.emit("changeInfoName", "kobe");
    }

    return {
      showInfoBtnClick,
    };
  },
};
</script>
