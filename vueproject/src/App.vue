<template>
  <div id="app">
    <div class="border">
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
          <select type= "number" 
          v-model="amount"
          name = "dropdown">
          <option>1</option>
          <option>2</option>
          <option>3</option>
          <option>4</option>
          <option>5</option>
          <option>6</option>
          <option>7</option>
          </select>
        </form>
      </div>
        <button @click="handleInput" >Add to Cart</button>
        <div class="cart">
          <p>Cart({{cart}})</p>
        </div>

      </div>
    </div>
          <img class="sun" src="./assets/sun.png" alt="sun image">
      <img class="cloud cloud1" src="./assets/cloud.png" alt="cloud image">
      <img class="cloud cloud3" src="./assets/cloud1.png" alt="cloud image">
      <img class="cloud cloud2" src="./assets/cloud.png" alt="cloud image">
      <img class="cloud cloud4" src="./assets/cloud2.png" alt="cloud image">
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
      amount: 1,
      // image: require("./assets/darkerflower.png"),
      alt:"Flower",
      cart:0,
      selectedIndex: 0,
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
      this.selectedVariant = index,
      console.log(index)
    },
    handleInput(){
      let amount = Number(this.amount)
      this.cart = this.cart + amount;
    }  
    // getCartValue(index){
    //    this.cart += index,
    //   this.selectedIndex = index
    //   //  console.log(selectedIndex)
    // }
    // // addToCart(){
    // //   this.$emit('add-to-cart', this.variants[this.selectedVariant].variantId)
    // // },    
    // // updateCart(id){
    // //   this.cart.push(id)
    // // }
  },
  computed:{
    title(){
      return this.brand + ' ' + this.product
    },
    image(){
      return this.variants[this.selectedVariant].variantImage
    },
    value(){
      return this.amount
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
  background: linear-gradient(#64a7e6 75%, #4fc24f 25%);
  width:100vw;
  height:100vh;
  margin:0 auto;
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
  width:60vw;
  height:50vh;
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
.cart {
  display: flex;
  flex-direction:column;
  justify-content: center;
  border: 1px solid #d8d8d8;
  background-color:  rgba(238, 238, 238, 0.267);
  padding: 5px 20px;
  margin-top:3rem;
}

button {
  margin-top: 30px;
  border: none;
  background-color: #431eea;
  color: white;
  height: 2rem;
  width: 100px;
  font-size: 14px;
}
.border {
  /* background-color: rgba(183, 0, 255, 0.267); */
  margin:0 auto;
  width:80vw;
  height:70vh;
      display: flex;
    align-items: center;
    justify-content: center;

}
.sun, 
.cloud{
  position:absolute;
  float:left;
  border:none;
  box-shadow:none;
}
.sun{
    width:15vw;
  left:0;
  top:0;
}
.cloud{
  width:10vw;
  opacity:0.5;
}
.cloud1{
  top:0;
  left:20vw;
}
.cloud2{
  top:2vh;
  left:60vw;
  opacity:0.7;
}
.cloud3{
  top:0;
  left:40vw;
  opacity:0.7;
}
.cloud4{
  top:2vw;
  left:80vw;
  opacity:.9;
}
</style>
