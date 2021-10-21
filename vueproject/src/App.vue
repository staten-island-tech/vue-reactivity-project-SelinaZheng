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

      </div>
    </div>
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
.colors-box{
  display: grid;
  grid: repeat(2, 60px) / auto-flow 80px;
}
.colors{
  width:2rem;
  height:2rem;
  margin-top:0.1rem;
}

</style>
