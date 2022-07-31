<script>
export default {
  setup() {
    function ShowInfoFoo() {
      console.log("showinfo foo function");
    }

    return {
      ShowInfoFoo,
    };
  },
};
</script>

<template>
  <div>ShowInfo</div>
</template>
