<template>
  <div
    class="flex flex-col items-center p-4 m-4 space-y-4 border prose-montserrat"
  >
    <h3>Atoms examples</h3>

    <AppButton variant="contained" size="medium" icon="left"
      ><template #icon><AppHomeIcon /></template>This is a really long
      sentence</AppButton
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
    <AppStepLine :current="step" :numStep="3" />
    <div class="flex flex-row space-x-4 prose-montserrat">
      <button
        class="p-2 border rounded shadow-md  button border-primary-base hover:bg-primary-light"
        @click="step--"
        :disabled="step < 2"
      >
        -
      </button>
      <button
        class="p-2 border rounded shadow-md  button border-primary-base hover:bg-primary-light"
        @click="step++"
        :disabled="step > 3 - 1"
      >
        +
      </button>
    </div>
    <AppCard
      :open="openCard"
      @close="openCard = false"
      variant="confirm"
      title="Title"
    >
      <template #header>Title</template>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Accusantium
        iste impedit minus, sapiente ipsum nihil? Non quisquam praesentium
        fugiat pariatur, voluptatem quos nisi, tempore aspernatur veritatis
        voluptates, dolorum nobis vel!
      </p>
    </AppCard>
    <AppButton variant="shaded" @click="openCard = !openCard"
      >Open
      <pre> AppCard </pre>
    </AppButton>
    <AppAlert variant="error" :open="openAlert" @close="openAlert = false"
      >Ceci est une alerte</AppAlert
    >
    <AppButton variant="shaded" @click="openAlert = !openAlert"
      >Open
      <pre> AppAlert </pre>
    </AppButton>
  </div>
</template>

<script>
import AppLink from "~/components/atoms/AppLink";
import AppError from "~/components/atoms/AppError";
import AppButton from "~/components/atoms/AppButton.vue";
import AppInputFrame from "~/components/atoms/AppInputFrame.vue";
import AppHomeIcon from "~/components/atoms/icons/AppHomeIcon.vue";
import AppCheckbox from "~/components/atoms/AppCheckbox.vue";
import AppStepLine from "~/components/molecules/AppStepLine.vue";
import AppCard from "~/components/organisms/AppCard.vue";
import AppAlert from "~/components/organisms/AppAlert.vue";
export default {
  components: {
    AppInputFrame,
    AppLink,
    AppError,
    AppButton,
    AppHomeIcon,
    AppCheckbox,
    AppStepLine,
    AppCard,
    AppAlert,
  },
  data() {
    return {
      step: 1,
      openCard: false,
      openAlert: false,
    };
  },
};
</script>
<style scoped></style>
