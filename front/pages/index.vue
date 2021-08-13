<template>
  <div class="w-screen h-screen">
    <Flag class="w-full h-full" />
  </div>
</template>

<script>
import Flag from "../components/organisms/Flag.vue";

export default {
  components: {
    Flag,
  },
  mounted() {
    this.$nuxt.$on("FlagClick", () => {
      // this.GotoEdit();
      this.$nuxt.router.push("/edit");
    });
  },
};
</script>

<style scoped></style>
