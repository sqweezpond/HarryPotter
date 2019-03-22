<template>
    <div>
        <nav class="navbar sticky-top bg-nav">
            <div class="container">
                <router-link :to="{ name: 'Home' }">
                <img src="../assets/hp.jpg" class="img-nav" />
                </router-link>
                <router-link :to="{ name: 'Cart'}" class="cart-size">
                <div class="form-inline">
                    <i class="fas fa-shopping-cart"></i>
                    <div id="" class="ml-2 cart-num">1</div>
                </div>
                </router-link>
            </div>
        </nav>
    </div>
</template>

<script>
export default {
    name: 'Navbar'
}
</script>
