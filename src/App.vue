<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import axios from "axios";
import { store } from "./store";

export default {
  components: {
    AppHeader,
    AppMain,
  },
  data: () => ({
    store
  }),

  mounted() {
    store.loading = true;
    axios.get(store.apiURL).then((resp) => {
      this.store.cards = resp.data.data;
      store.loading = false;
    })
  }

}

</script>

<template>
  <AppHeader title="Yu-Gi-Oh Api"></AppHeader>
  <AppMain></AppMain>
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>