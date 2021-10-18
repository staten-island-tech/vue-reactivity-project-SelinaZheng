<template>
  <div id="app">
    <div class="nav-bar"></div>
    <div class="flex">
      <div class="image">
        <img v-bind:src="image" v-bind:alt="alt">
      </div>
      <div class="colors">

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
      // alt:
      variants: [
       {
       variantId: 1,
       variantColor: 'Dark Blue',
       variantImage: './assets/darkerflower.png',
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
</style>
