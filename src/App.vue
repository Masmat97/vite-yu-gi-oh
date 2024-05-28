<script>

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import store from './data/store.js';
import axios from 'axios';

export default {
  components: {
    AppHeader,
    AppMain,
  },
  props: {

  },
  data() {
    return {
      store,
      searchString: "",
    }
  },
  methods: {
    getPersonaggi() {
      axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0" + this.searchString).then(risultato =>{
        this.store.personaggi = risultato.data.results;

      });

    }
  },
  created() {
    this.getPersonaggi();
  },
  mounted() {

  }
}
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style scoped></style>