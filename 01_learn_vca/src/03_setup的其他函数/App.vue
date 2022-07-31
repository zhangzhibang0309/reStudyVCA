<template>
  <show-info :info="info" @changeInfoName="changeInfoName"></show-info>
</template>

<script>
import { reactive } from "vue";
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

    return {
      info,
      changeInfoName,
    };
  },
};
</script>
