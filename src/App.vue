<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppSearchBar from './components/AppSearchBar.vue';
import axios from 'axios';

export default {
  components: {
    AppHeader,
    AppMain,
    AppSearchBar,
  },
  data() {
    return {
      apiURL: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0',
      selectedStatus: '',
      cards: [],
    };
  },
  mounted() {
    this.getCards();
  },
  methods: {
    getCards() {
      const params = {};
      if (this.selectedStatus) {
        params.archetype = this.selectedStatus;
      }
      axios.get(this.apiURL, {
        params,
      })
        .then(response => {
          this.cards = response.data.data;
        })
        .catch(error => {
          console.log(error);
        });
    },
    handleFilter(selectedStatus) {
      this.selectedStatus = selectedStatus;
      this.getCards();
    },
  },
};
</script>

<template>
  <div>
    <AppHeader title="Yu-Gi-Oh Api"></AppHeader>
    <AppSearchBar @filter="handleFilter"></AppSearchBar>
    <AppMain :cards="cards"></AppMain>
  </div>
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
