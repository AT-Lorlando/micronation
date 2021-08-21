<template>
  <div class="flex flex-col space-y-4 place-items-center prose-montserrat">
    <h1 class="text-center">Fouloscopie Auth PoC</h1>
    <AppButton
      variant="contained"
      size="medium"
      @click="showAuthContainer = true"
      >Se connecter</AppButton
    >
    <!-- <AppCard
      title="Portail d'authentification Fouloscopie"
      :open="showLogIn"
      @close="showLogIn = false"
      id="authContainer"
    ></AppCard> -->
  </div>
</template>

<script>
// import AppCard from "~/components/organisms/AppCard.vue";
// import AuthentificationComp from "~/assets/authComponent";

export default {
  components: { AppButton, AppError, },
  data() {
    return {
      showLogIn: false,
    };
  },
  methods: {
    showAuthContainer() {
      this.showLogIn = true;
      //   AuthentificationComp({
      //     prefilledEmail: "foo@bar.com",

      //     onLogin: function (email) {
      //       console.log("User logged in with email:", email);
      //     },
      //   }).render("#authContainer");
    },
  },
};
</script>

<style></style>
