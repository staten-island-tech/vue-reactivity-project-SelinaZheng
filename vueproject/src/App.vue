<template>
  <div id="app">
    <div class="nav-bar"></div>
    <div class="flex">
      <div class="image">
        <img :src="image" v-bind:alt="alt">
      </div>
      <div class="colors"
      v-for="(variant, index) in variants" 
      :key="variant.variantId"
      :style="{ backgroundColor: variant.variantColor }"
      @mouseover="updateProduct(index)"
      >
        <p class="name">{{ variant.variantColor }}</p>
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
      product: 'Flowers',
      selectedVariant: 0,
      image: require("./assets/darkerflower.png"),
      alt:"Flower",
      variants: [
       {
       variantId: 1,
       variantColor: 'Dark Blue',
       variantImage: require('./assets/darkerflower.png'),
       variantQuantity: 10     
       },
       {
       variantId: 2,
       variantColor: 'Purple',
       variantImage: './assets/purpleflower.png',
       variantQuantity: 0     
        },
      {
       variantId: 3,
       variantColor: 'Light Blue',
       variantImage: './assets/lightflower.png',
       variantQuantity: 0     
        },
       {
       variantId: 4,
       variantColor: 'Hot Pink',
       variantImage: './assets/hotterflower.png',
       variantQuantity: 0     
        },
      {
       variantId: 5,
       variantColor: 'Pink',
       variantImage: './assets/pinkflower.png',
       variantQuantity: 0     
        },
        {
       variantId: 6,
       variantColor: 'Red',
       variantImage: './assets/redflower.png',
       variantQuantity: 0     
        },
        {
       variantId: 7,
       variantColor: 'Orange',
       variantImage: './assets/orangeflower.png',
       variantQuantity: 0     
        },
        {
       variantId: 8,
       variantColor: 'Yellow',
       variantImage: './assets/yellowflower.png',
       variantQuantity: 0     
        },
        {
       variantId: 9,
       variantColor: 'Pink',
       variantImage: './assets/pinkflower.png',
       variantQuantity: 0     
        },
      ],
    };
  },

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
.colors{
  margin-top: 10px;
  width: 40%;
}

</style>
