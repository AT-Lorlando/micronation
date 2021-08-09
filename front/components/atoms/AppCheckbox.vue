<template>
  <div class="prose-roboto">
    <input
      type="checkbox"
      id="checkbox"
      :checked="checked"
      @change="$emit('change', $event.target.checked)"
    />
    <label class="text-grey-dark body-1">{{ label }}</label>
  </div>
</template>

<script>
export default {
  name: "AppCheckbox",
  props: {
    checked: {
      type: Boolean,
      default: false,
    },
    label: {
      required: true,
      type: String,
      default: undefined,
    },
  },
};
</script>

<style scoped lang="postcss">
/*Styling checkbox with a workaround as it's not a html element meant to be styled */

#checkbox {
  @apply: border border-primary-base;
}
</style>
