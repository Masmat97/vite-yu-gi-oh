<script>


export default {
    name: "ProductCard",
    props: ["prodotto"],
    
}
</script>

<template>
    <div class="productCard">
        <img :src="prodotto.src" alt="">
        <p>{{ prodotto.series }}</p>
    </div>
</template>

<style scoped>
.productCard {
    width: 25%;
}</style>