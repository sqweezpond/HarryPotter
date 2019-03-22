<template>
  <div id="app">
     <link rel="stylesheet" 
        href="https://use.fontawesome.com/releases/v5.2.0/css/all.css" 
        integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ" 
        crossorigin="anonymous">

      <nav class="navbar sticky-top bg-nav">
        <div class="container">
            <router-link :to="{ name: 'Home', params: { msg } }">
              <img src="./assets/hp.jpg" class="img-nav" />
            </router-link>
            <router-link :to="{ name: 'Cart', params: { msg } }" class="cart-size">
              <div class="form-inline">
                <i class="fas fa-shopping-cart"></i>
                <div id="" class="ml-2 cart-num">1</div>
              </div>
            </router-link>
        </div>
      </nav>

    <router-view/>
  </div>
</template>

<script>
  export default {
    name: 'App',
    data () {
      return {
        msg: ['1','2','3','4']
      }
    }
  }
</script>