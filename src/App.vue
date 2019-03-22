<template>
  <div id="app">
     <link rel="stylesheet" 
        href="https://use.fontawesome.com/releases/v5.2.0/css/all.css" 
        integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ" 
        crossorigin="anonymous">
        <Navbar></Navbar>
        <router-view :cart="cart" />
  </div>
</template>

<script>

  // Vue.component('Navbar', './component/Nav.vue')
  import Navbar from './component/Nav.vue' 

  export default {
    name: 'App',
    components:{Navbar},
    data () {
      return {
        cart: {},
        cartcount:0
      }
    }
  }
</script>