<script>
import { reactive, computed } from "vue";

export default {
  setup() {
    // 1.定义数据
    const names = reactive({
      firstName: "kobe",
      lastName: "bryant",
    });

    // const fullName = computed(() => {
    //   return names.firstName + " " + names.lastName;
    // });

    const fullName = computed({
      set(newValue) {
        const tmpNames = newValue.split(" ");
        names.firstName = tmpNames[0];
        names.lastName = tmpNames[1];
      },
      get() {
        return names.firstName + " " + names.lastName;
      },
    });

    function setFullName() {
      fullName.value = "我改 变了";
    }

    return {
      fullName,
      setFullName,
    };
  },
};
</script>

<template>
  <h2>{{ fullName }}</h2>
  <button @click="setFullName">更改fullname</button>
</template>
