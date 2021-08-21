<template>
  <div
    class="grid items-center w-full grid-cols-2 py-2 bg-white shadow-md px-7"
  >
    <div class="flex flex-row items-center justify-start space-x-8">
      <AppIconHome class="hidden lg:block" />
      <div
        class="cursor-pointer lg:pointer-events-none lg:hidden"
        @click="toggleMobileMenu"
      >
        <AppIconHome />
        <div v-if="openMobileNav">yo</div>
      </div>
      <AppButton
        :to="{ name: 'edit' }"
        size="medium"
        variant="contained"
        class="hidden bg-primary-dark lg:block"
      >
        Editer le drapeau
      </AppButton>
      <AppButton class="hidden lg:block" :to="{ name: 'index' }"
        >Accueil</AppButton
      >
      <AppButton class="hidden lg:block" :to="{ name: 'a-propos' }"
        >A propos</AppButton
      >
    </div>
    <div v-if="loggedIn" class="flex justify-end">
      <AppButton icon="left" variant="contained" class="bg-primary-dark"
        ><template #icon><AppPersonIcon /></template
        ><span class="lg:block">Pseudo</span></AppButton
      >
    </div>
    <div v-else class="flex justify-end space-x-8">
      <AppButton variant="outlined" size="medium" class="hidden lg:block"
        >S'inscrire</AppButton
      >
      <AppButton variant="outlined" size="medium" class="lg:hidden"
        ><template #icon><AppRegisterIcon /></template
      ></AppButton>
      <AppButton
        variant="contained"
        class="hidden bg-primary-dark lg:block"
        size="medium"
        >Se connecter</AppButton
      >
      <AppButton
        variant="contained"
        size="medium"
        class="bg-primary-dark lg:hidden"
        ><template #icon><AppLogInIcon /></template
      ></AppButton>
    </div>
  </div>
</template>

<script>
import AppButton from "../atoms/AppButton.vue";
import AppIconHome from "../atoms/icons/AppHomeIcon.vue";
import AppPersonIcon from "../atoms/icons/AppPersonIcon.vue";
import AppLogInIcon from "../atoms/icons/AppLogInIcon.vue";
import AppRegisterIcon from "../atoms/icons/AppRegisterIcon.vue";

export default {
  components: {
    AppIconHome,
    AppButton,
    AppPersonIcon,
    AppLogInIcon,
    AppRegisterIcon,
  },
  name: "TheHeader",
  props: {
    loggedIn: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      openMobileNav: false,
    };
  },
  methods: {
    toggleMobileMenu() {
      this.openMobileNav = true;
    },
  },
};
</script>

<style></style>
