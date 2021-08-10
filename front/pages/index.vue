<template>
  <div
    class="flex flex-col items-center p-4 m-4 space-y-4 border prose-montserrat"
  >
    <h3>Atoms examples</h3>

    <AppButton variant="contained" size="medium" icon="left"
      ><template #icon><AppHomeIcon /></template>Master</AppButton
    >
    <AppInputFrame
      label="Oui."
      :select="false"
      :border="true"
      :options="[{ name: 'Placeholder', value: 5 }]"
      errorMessage="P'tite erreur des familles"
    ></AppInputFrame>
    <AppLink link="https://www.youtube.com/user/dirtybiology"
      >This is a link</AppLink
    >
    <AppError>This is an error</AppError>
    <AppCheckbox label="oui" />
    <AppStep />
    <TheHeader />
  </div>
</template>

<script>
import AppLink from "~/components/atoms/AppLink";
import AppError from "~/components/atoms/AppError";
import AppButton from "~/components/atoms/AppButton.vue";
import AppInputFrame from "~/components/atoms/AppInputFrame.vue";
import AppHomeIcon from "~/components/atoms/icons/AppHomeIcon.vue";
import TheHeader from "~/components/organisms/TheHeader.vue";
import AppCheckbox from "~/components/atoms/AppCheckbox.vue";
import AppStep from "~/components/atoms/AppStep.vue";

export default {
  components: {
    AppInputFrame,
    AppLink,
    AppError,
    AppButton,
    AppHomeIcon,
    TheHeader,
    AppCheckbox,
    AppStep,
  },
};
</script>
<style scoped></style>
