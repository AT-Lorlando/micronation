<template>
  <div class="p-4 space-y-4 bg-white rounded-lg prose-roboto">
    <span class="prose-montserrat"
      ><h6>{{ title }}</h6></span
    >
    <div class="body-1"><slot></slot></div>
    <div :class="actionBarClass">
      <AppButton
        variant="outlined"
        :class="this.isConfirm ? 'border-negative-dark' : 'border-black'"
        v-if="isChoice || isConfirm"
        >Annuler</AppButton
      >
      <AppButton
        :class="variant === 'confirm' ? 'bg-positive-dark' : 'bg-primary-dark'"
        variant="contained"
        >{{ actionName }}</AppButton
      >
    </div>
  </div>
</template>

<script>
import AppButton from "~/components/atoms/AppButton.vue";

export default {
  name: "AppCard",
  components: { AppButton },
  props: {
    variant: {
      type: String,
      default: "info",
      validator(value) {
        return ["info", "confirm", "choice"].includes(value);
      },
    },
    title: {
      type: String,
      default: undefined,
      required: true,
    },
    actionName: {
      type: String,
      default: "Continuer",
    },
  },
  computed: {
    isInfo() {
      return this.variant === "info";
    },
    isChoice() {
      return this.variant === "choice";
    },
    isConfirm() {
      return this.variant === "confirm";
    },
    actionBarClass() {
      const actionBarClasses = ["w-full flex flex-row"];
      if (this.isInfo) actionBarClasses.push("justify-end");
      else actionBarClasses.push("justify-between");

      return actionBarClasses.join(" ");
    },
  },
};
</script>

<style></style>
