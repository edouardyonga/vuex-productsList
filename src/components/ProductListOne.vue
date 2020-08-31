<template>
    <div id="product-list-one">
        <h2>Product List One</h2>
        <ul>
            <li v-for="(product, index) in saleProducts" :key="index">
                <span class="name">{{ product.name }}</span>
                <span class="price">£{{ product.price }}</span>
            </li>
        </ul>
        <button @click="reducePrice(4)">Reduce Price</button>
    </div>    
</template>
<script>

export default {
    computed:{
        products(){
            return this.$store.state.products;
        },
        saleProducts(){
            return this.$store.getters.saleProducts
        }

    },
    methods:{
        reducePrice: function(payload) {
            this.$store.dispatch('reducePrice',payload)
        }
    }
    
}
</script>
<style scoped>
#product-list-one{
    float: left;
    margin-top: 10%;
    margin-left: 20%;
}
</style>