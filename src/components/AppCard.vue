<script>

import ProductCard from './ProductCard.vue';
import store from '../data/store.js';

export default {
  components: {
    ProductCard
  },
  props: {
        character: Object
    },
  data() {
    return {
      store,
    }
  },
  methods: {

  },
  mounted() {

  }
}
</script>

<template>
  <div class="products">
    <div v-for="elemento in store.carte" class="productCard">
      <img :src="elemento.card_images[0].image_url_small" alt="">
      <h3>{{ elemento.name }}</h3>
      <p>{{ elemento.type }}</p>
    </div>
  </div>

</template>

<style scoped>
.products {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  margin-top: 2rem;
  background-color: orange;
  
}

.productCard {
  width: 15%;
  background-color: red;
  margin: 2rem;
}

.productCard>img {
  width: 100%;
}
</style>