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

    return {
      info,
      changeInfoName,
      roInfo,
      changeRoInfoName,
    };
  },
};
</script>
