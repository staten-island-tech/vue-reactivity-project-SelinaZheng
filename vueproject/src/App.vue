<template>
  <div id="app">
    <div class="nav-bar"></div>
    <div class="flex">
      <div class="image">
        <img :src="image" v-bind:alt="alt">
      </div>
      <div class="product-info">
        <h1>{{ title }}</h1>
        <div class="color-box">
            <div class="colors"
            v-for="(variant, index) in variants" 
            :key="variant.variantId"
            :style="{ backgroundColor: variant.variantColor }"
            @mouseover="updateProduct(index)"
            >
            </div>
        </div>
      </div>
      <div class="cart">
              <div class="quantity">
        <h4>Quantity</h4>
        <form>
          <select name = "dropdown">
          <option value = "1">1</option>
          <option value = "2">2</option>
          <option value = "3">3</option>
          <option value = "4">4</option>
          <option value = "5">5</option>
          <option value = "6">6</option>
          <option value = "7">7</option>
          </select>
        </form>
      </div>
        <button v-on:click="addToCart" >Add to Cart</button>
        <div class="cart">
          <p>Cart({{cart}})</p>
        </div>

      </div>
    </div>
    <div class="footer-bar"></div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {

  },
  data(){
    return{
      brand: "SITHS's",
      product: 'Flowers',
      selectedVariant: 0,
      // image: require("./assets/darkerflower.png"),
      alt:"Flower",
      variants: [
       {
       variantId: 1,
       variantColor: ' #00008b',
       variantImage: require('./assets/darkerflower.png'),
       variantQuantity: 10     
       },
       {
       variantId: 2,
       variantColor: 'Purple',
       variantImage: require('./assets/purpleflower.png'),
       variantQuantity: 0     
        },
      {
       variantId: 3,
       variantColor: '#ADD8E6',
       variantImage:  require('./assets/lightflower.png'),
       variantQuantity: 0     
        },
       {
       variantId: 4,
       variantColor: '	#FF69B4',
       variantImage:  require('./assets/hotterflower.png'),
       variantQuantity: 0     
        },
      {
       variantId: 5,
       variantColor: 'Pink',
       variantImage:  require('./assets/pinkflower.png'),
       variantQuantity: 0     
        },
        {
       variantId: 6,
       variantColor: 'Red',
       variantImage:  require('./assets/redflower.png'),
       variantQuantity: 0     
        },
        {
       variantId: 7,
       variantColor: 'Orange',
       variantImage:  require('./assets/orangeflower.png'),
       variantQuantity: 0     
        },
        {
       variantId: 8,
       variantColor: 'Yellow',
       variantImage:  require('./assets/yellowflower.png'),
       variantQuantity: 0     
        },
        {
       variantId: 9,
       variantColor: 'Pink',
       variantImage:  require('./assets/pinkflower.png'),
       variantQuantity: 0     
        },
      ],
    };
  },
  methods:{
    updateProduct(index){
      this.selectedVariant = index

    },
  },
  computed:{
    title(){
      return this.brand + ' ' + this.product
    },
    image(){
      return this.variants[this.selectedVariant].variantImage
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.nav-bar,
.footer-bar{
  height:2rem;
  background-color: #2c3e50;
  width:100%;
}
.footer-bar{
  position:fixed;
  bottom:4rem;
  left:0;
  text-align:center;

}
.flex{
  display: flex;
  flex-flow: wrap;
  padding: 1rem;
}
img{
  border: 1px solid #d8d8d8;
  width: 50%;
  margin: 40px;
  box-shadow: 0px 0.5px 1px #d8d8d8;
}
.image{
  width:50;
}
.image,
.product-info{
  margin-top: 10px;
  width: 40%;
}
.color-box{
  display: grid;
  grid: repeat(3, 4.5rem) / auto-flow 4.5rem;
  margin-top: 3rem;
}
.colors{
  width:75%;
  height:3.5rem;
  margin-top:0.1rem;
}

</style>
