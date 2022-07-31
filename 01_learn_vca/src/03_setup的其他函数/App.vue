<template>
  <show-info
    :info="info"
    :roInfo="roInfo"
    @changeInfoName="changeInfoName"
    @changeRoInfoName="changeRoInfoName"
    changeRoInfoName
  ></show-info>
</template>

<script>
import { reactive, readonly } from "vue";
import ShowInfo from "./ShowInfo.vue";

export default {
  components: {
    ShowInfo,
  },
  setup() {
    const info = reactive({
      name: "zz",
      age: 18,
    });
    function changeInfoName(payload) {
      info.name = payload;
    }

    const roInfo = readonly(info);
    function changeRoInfoName(payload) {
      info.name = payload;
    }

    // reactive相关的api（reactive是proxy对象）
    /**
     * isProxy 判断是否是reactive或者readonly对象
     * isReactive 见名知意义
     * isReadonly 见名知意义
     * toRaw 拿到原始对象，非代理
     * shallowReactive 浅层reactive，不代理嵌套对象
     * shallowReadonly 浅层readonly,同上
     */

    return {
      info,
      changeInfoName,
      roInfo,
      changeRoInfoName,
    };
  },
};
</script>
