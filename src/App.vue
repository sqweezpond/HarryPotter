
<template>
  <div id="app">
     <link rel="stylesheet" 
        href="https://use.fontawesome.com/releases/v5.2.0/css/all.css" 
        integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ" 
        crossorigin="anonymous">

      <nav class="navbar sticky-top bg-nav">
        <div class="container">
            <router-link to="/"><img src="./assets/hp.jpg" class="img-nav" alt=""/></router-link>
            <router-link to="/Cart" :AddCart="AddCart">
              <button type="button" prop-name="AddCart" class="btn btn-cart btn-outline-light"><i class="fas fa-shopping-cart icon-size"></i></button>
            </router-link>
        </div>
      </nav>

    <router-view/>
  </div>
</template>
