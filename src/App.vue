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
      axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=40&offset=0" + this.searchString).then(risultato => {
        this.store.carte = risultato.data.data;
        console.log(risultato.data.data)
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
  <AppHeader/>
  <input type="text">
  <AppMain />
</template>

<style scoped></style>