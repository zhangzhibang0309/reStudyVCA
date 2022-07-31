<template>
  <div>
    <p>ShowInfo:{{ info }}</p>
    <!-- 代码没有错误，但是违背规范（单项数据流规范） -->

    <!-- 正确的做法：符合单项数据流规范，子组件不要修改父组件传过来的值 -->
    <button @click="showInfoBtnClick">修改名字</button>
  </div>
  <hr />

  <div>
    <p>ShowInfo:{{ roInfo }}</p>
    <!-- readonly不可修改 -->
    <button @click="roInfo.name = 'kobe'">修改名字（不规范）</button>
    <!-- 正确的做法 -->
    <button @click="showRoInfoBtnClick">修改名字（不规范）</button>
  </div>
</template>

<script>
export default {
  props: {
    // reactive数据
    info: {
      type: Object,
      default: () => ({}),
    },
    // readonly数据
    roInfo: {
      type: Object,
      default: () => ({}),
    },
  },
  emits: ["changeInfoName", "changeRoInfoName"],
  setup(props, context) {
    function showInfoBtnClick() {
      context.emit("changeInfoName", "kobe");
    }
    function showRoInfoBtnClick() {
      context.emit("changeRoInfoName", "james");
    }

    return {
      showInfoBtnClick,
      showRoInfoBtnClick,
    };
  },
};
</script>
