<template>
  <div>
    <AppInputFrame
      :select="select"
      :border="border"
      :placeholder="placeholder"
      :options="options"
      @input="$emit('input', $event)"
    ></AppInputFrame>
    <AppError v-if="errorMessage">{{ errorMessage }}</AppError>
  </div>
</template>

<script>
import AppError from "../atoms/AppError.vue";
import AppInputFrame from "../atoms/AppInputFrame.vue";
export default {
  name: "LabeledInputFrame",
  components: { AppInputFrame, AppError },
  props: {
    label: {
      type: String,
      required: true,
      default: undefined,
    },
    errorMessage: {
      type: String,
      default: undefined,
    },
    /* AppInputFrame props */
    select: {
      type: Boolean,
      default: false,
    },
    border: {
      type: Boolean,
      default: true,
    },
    placeholder: {
      type: String,
      default: "",
    },
    options: {
      type: Array,
      default: undefined,
    },
  },
};
</script>

<style></style>
