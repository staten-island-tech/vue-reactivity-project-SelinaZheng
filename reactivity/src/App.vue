<template>
  <div id="app">
    <!-- <div class="flex-box">
       <div class="product-image">
        <img v-bind:src="image" v-bind:alt="alt">
       </div>
      <div class="product-info">
       <h1>{{ title }}</h1>
        <p v-show="onSale">On Sale!</p>
        <p v-if="inventory > 10">In Stock</p>
        <p v-else-if="inventory <= 10 && inventory > 0">Almost Sold Out!</p>
        <p v-else>Out of Stock</p>
       <button v-on:click="addToCart">Add to Cart</button>
        <div class="cart">
          <p>Cart({{ cart }})</p>
        </div>
      </div>
    </div> -->
  </div>
</template>

<script>
export default {
  name: 'App',
  components:{
      el: "#app",
  //element property^
  data: {
    brand: "Selina's Cool",
    product: "Socks",
    image: "./assets/vmSocks-green.jpg",
    alt: "Green Socks",
    inventory: 10,
    onSale: false,
    cart: 0,
  },
  methods: {
    addToCart () {
      this.cart += 1;
    },
  },
  computed: {
    title() {
      return this.brand + " " + this.product;
    },
  },
  }
}
</script>
<style>

</style>