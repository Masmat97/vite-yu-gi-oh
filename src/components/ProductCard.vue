<script>
import AppCard from './AppCard.vue';
import store from '../data/store.js';

export default {
    name: "ProductCard",

    components: {
        AppCard,
    },
    data() {
        return {
            store
        }
    }
}
props: { }

</script>

<template>
    <AppCard v-for="elemento in StorageEvent.carte" :character="personaggio" />
</template>

<style scoped>
.productCard {
    width: 25%;
}
</style>