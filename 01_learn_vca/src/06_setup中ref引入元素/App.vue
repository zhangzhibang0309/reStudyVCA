<script>
import { ref, onMounted } from "vue";
import ShowInfo from "./ShowInfo.vue";

export default {
  components: {
    ShowInfo,
  },
  setup() {
    const titleRef = ref();
    const btnRef = ref();
    const showInfoRef = ref();

    // dom挂载后访问dom节点
    onMounted(() => {
      console.log(titleRef.value);
      console.log(btnRef.value);
      console.log(showInfoRef.value);

      showInfoRef.value.ShowInfoFoo();
    });

    return {
      titleRef,
      btnRef,
      showInfoRef,
    };
  },
};
</script>

<template>
  <h2 ref="titleRef">title</h2>
  <button ref="btnRef">btn</button>
  <show-info ref="showInfoRef"></show-info>
</template>
