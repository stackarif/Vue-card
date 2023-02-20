<template>
  <div>
    <div class="product-card">
        <div class="product-card_title">
            <div>
                {{ product.name }}

            </div>
            <img src="../assets/img/star.png" v-if="product.addedToFavourite" @click="toggleFavourite"  alt="star">
            <img src="../assets/img/un-star.png" v-else @click="toggleFavourite" alt="star">

        </div>
        <div class="product-card_body">
            <img :src="product.thumbnail" alt="">
            <p>{{ product.price }}</p>

        </div>

        <div class="product-card_footer">
            <button @click="handleBuyNowClick">Buy Now</button>
            <button @click="handleAddToCartClick">Add to Cart</button>

        </div>
    </div>

  </div>
</template>

<script>
export default {
    props: {product:{type:Object, default:()=>({})}},
    methods:{
        handleBuyNowClick(){
            this.$emit("buy-now-clicked", this.product);
        },
        handleAddToCartClick(){
            this.$emit("add-to-cart-clicked", this.product);
        },
        toggleFavourite(){
            this.$emit("toggle-favourite",this.product)
        }
    }

};
</script>

<style>
.product-card{
    width:300px;
    border:1px solid #006f88;
    min-height: 200px;
    margin:22px auto;
}
.product-card_title{
    background: #167db1;
    padding: 5px 11px;
    color: #fff;
    display:flex;
    justify-content:space-between;
    align-items: center;
}
.product-card_body{
    padding:11px;
    text-align: center;
}
.product-card_body img{
    height: 111px;
}
ul li{
    list-style: none;
}
.product-card_footer{
    background: #e3e3e3;
    padding: 5px 11px;
    text-align: center;
}
button{
    margin: 8px;
    padding: 4px;
}

</style>