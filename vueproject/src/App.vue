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
      image:"./assets/flower.jpg",
      alt:,
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
