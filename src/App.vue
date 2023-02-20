<template>
  <header>
    <h2>{{ msg }}</h2>
  </header>
  <div>
    <product-card v-for="product in products" 
    :key="product.name"
    :product="product" 
    @buy-now-clicked="buyNow"
    @add-to-cart-clicked="addToCart"
    @toggle-favourite="handleToggle"
    >
    
    </product-card>

 

  </div>
</template>

<script>
import ProductCard from "./components/ProductCard.vue";
export default {
  data(){
    return {
      msg: "Welcome to vue3 Bangla Tutorial",
      products:[
        {
          name: "Apple iPhone 12 Pro",
          thumbnail: "https://fdn2.gsmarena.com/vv/bigpic/apple-iphone-12-pro-max-.jpg",
          price: "৳161999",
          addedToFavourite: true
        },
        {
          name: "Samsung Galaxy S23+",
          thumbnail: "https://fdn.gsmarena.com/imgroot/news/23/02/vivo-v27-series-global-launch-revealed/inline/-x500/gsmarena_001.jpg",
          price: "৳261999",
          addedToFavourite: false

        },
        {
          name: "vivo Y56 5G announced",
          thumbnail: "https://fdn.gsmarena.com/imgroot/news/23/02/vivo-y-56-ofic/inline/-x320/gsmarena_001.jpg",
          price: "৳361999",
          addedToFavourite: true

        },
      
      ],
    }
  },
  methods:{
    buyNow(product){
      console.log(product)

    },
    addToCart(){
      console.log("Adding....")

    },
    handleToggle(product){
      product.addedToFavourite = !product.addedToFavourite;
    }
  },
  components:{
    ProductCard
  }

};
</script>

<style>
*{
  margin:0;
  padding:0;
  box-sizing: border-box;
}
ul{
  margin-left:22px;
}
body{
  font-family: sans-serif;
  line-height: 1.8;
}
header{
  background-color: #1f2c46;
  color:#41b883;
  font-size:22px;
  padding:22px;
}
header h2{
  text-align: center;
}

</style>
