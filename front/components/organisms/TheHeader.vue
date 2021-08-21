<template>
  <div class="grid w-full grid-cols-2 py-2 bg-white shadow-md px-7">
    <div class="flex flex-row items-center justify-start space-x-8">
      <AppIconHome classs="w-10 h-10" />
      <AppButton
        :to="{ name: 'edit' }"
        size="medium"
        variant="contained"
        class="hidden bg-primary-dark md:block"
      >
        Editer le drapeau
      </AppButton>
      <AppButton :to="{ name: 'index' }">Accueil</AppButton>
      <AppButton :to="{ name: 'a-propos' }">A propos</AppButton>
    </div>
    <div v-if="loggedIn" class="flex justify-end">
      <AppButton icon="left" variant="contained" class="bg-primary-dark"
        ><template #icon><AppPersonIcon /></template>Pseudo</AppButton
      >
    </div>
    <div v-else class="flex justify-end space-x-8">
      <AppButton variant="outlined" size="medium">S'inscrire</AppButton>
      <AppButton variant="contained" class="bg-primary-dark" size="medium"
        >Se connecter</AppButton
      >
    </div>
  </div>
</template>

<script>
import AppButton from "../atoms/AppButton.vue";
import AppIconHome from "../atoms/icons/AppHomeIcon.vue";
import AppPersonIcon from "../atoms/icons/AppPersonIcon.vue";
import screenIs from "~/assets/screenIs";

export default {
  components: { AppIconHome, AppButton, AppPersonIcon },
  name: "TheHeader",
  props: {
    loggedIn: {
      type: Boolean,
      default: false,
    },
  },
  mounted() {},
  computed: {
    maxBreakpoint() {
      const { theme: currentTheme } = require("@/tailwind.config.js");
      console.log(currentTheme.extend.screens);
      return true;
    },
  },
};
</script>

<style></style>
