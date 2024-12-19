<template>
</template>

<script>
import About from "@/components/modal/About.vue";
import Contribute from "@/components/modal/Contribute.vue";
import { version } from "../../../package.json";

export default {
  name: "AppFooter",
  data: () => ({
    version,
    links: [
    ],
  }),
  methods: {
    
    about() {
      this.$refs.about.open();
    },
    contribute() {
      this.$refs.contribute.open();
    },
  },
  components: { Contribute, About },
};
</script>

<style></style>
