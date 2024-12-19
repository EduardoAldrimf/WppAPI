<template>
</template>

<script>
import copyToClipboard from "@/helpers/copyToClipboard";
export default {
  name: "SettingsModal",
  data: () => ({
    dialog: false,
    copied: false,
    connection: null,
  }),
  methods: {
    copy() {
      if (this.copied) return;
      const url = new URL(window.location.href);
      const connection = JSON.stringify(this.connection);
      const base64 = btoa(connection);
      url.searchParams.set("connection", base64);

      copyToClipboard(url.href);

      this.copied = true;
      setTimeout(() => {
        this.copied = false;
      }, 2000);
    },
    open({ host, globalApiKey }) {
      this.dialog = true;
      this.connection = { host, globalApiKey };
    },
  },
};
</script>
