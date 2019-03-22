<template>
  <div class="mt-5">
    <div class="container">

      <div class="row">
        Add Cart : {{ cart }}
      </div>

      <div class="row mt-4">
        <ul class="col-lg-8">
          <li class="list-group-item" v-for="book in incart" :key="incart">
            <div class="row">
              <div class="col-md-2 text-center"><img v-bind:src="book.cover" class="img-book" alt="" /></div>
              <div class="col-md-3 text-center">{{book.title}}</div>
              <div class="col-md-2 text-center">{{book.price}}</div>
              <div class="col-md-3 text-center">
                <div class="btn-group" role="group">
                  <button type="button" class="btn btn-outline-dark">-</button>
                  <input type="text" class="form-qty form-control" id="" v-bind:value="book.count">
                  <button type="button" class="btn btn-outline-dark">+</button>
                </div>
              </div>
              <div class="col-md-2 text-center">
                <button type="button" class="btn btn-outline-danger">
                  <i class="fas fa-trash-alt"></i>
                </button>
              </div>
            </div>
          </li>
        </ul>

        <ul class="col-lg-4 mt-4 mt-lg-0 text-right">
          <li class="list-group-item pb-4">
            <div class="row">
              <div class="col-md-4 col-6 mt-2">Price</div>
              <div class="col-md-6 col-6 text-right total-border mt-2">฿200</div>
            </div>
            <div class="row">
              <div class="col-md-4 col-6 mt-2">Discount</div>
              <div class="col-md-6 col-6 text-right total-border mt-2">฿180</div>
            </div>
            <div class="row">
              <div class="col-md-4 col-6 mt-2">Total</div>
              <div class="col-md-6 col-6 text-right total-border mt-2">฿180</div>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Cart',
    props: ['cart'],
    data() {
      return {
        incart: this.cart
      }
    },
    mounted() {}
  }

</script>
