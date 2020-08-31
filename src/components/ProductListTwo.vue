<template>
    <div id="product-list-two">
        <h2>Product List Two</h2>
        <ul>
            <li v-for="(product, index) in saleProducts" :key="index">
                <span class="name">{{ product.name }}</span>
                <span class="price">£{{ product.price }}</span>
            </li>
        </ul>
        <button @click="reducePrice">Reduce Price</button>
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
        reducePrice: function() {
            this.$store.commit('reducePrice')
        }
    }

    
}
</script>

<style scoped>
#product-list-two{
    float: right;
    margin-top: 10%;
    margin-right: 20%;
}
</style>