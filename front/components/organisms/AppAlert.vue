<template><div class=""></div></template>

<script>
export default {
  name: "AppAlert",
  props: {
    variant: {
      type: String,
      default: "info",
      validator(value) {
        return ["info", "error"].includes(value);
      },
    },
  },
  computed:{

  }
};
</script>

<style></style>
