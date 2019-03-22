<template>
    <div class="container mt-5">

      <div class="row">
        <table class="table table-light table-responsive-md">
          <tbody v-for="book in this.cart" class="text-center">
              <td><img v-bind:src="book.cover" class="img-book" alt="" /></td>
              <td>{{book.title}}</td>
              <td>{{book.price}}</td>
              <td>
                <div class="btn-group" role="group">
                  <button type="button" class="btn btn-outline-dark">-</button>
                  <input type="text" class="form-qty form-control" id="" v-bind:value="book.count">
                  <button type="button" class="btn btn-outline-dark">+</button>
                </div>
              </td>
              <td>
                <button type="button" class="btn btn-outline-danger">
                  <i class="fas fa-trash-alt"></i>
                </button>
              </td>
          </tbody>
        </table>
      </div>


      <div class="row justify-content-end">
          <div class="col-lg-4 pb-4">
            <div class="row">
              <div class="col-6 text-right mt-2">Price</div>
              <div class="col-6 total-border mt-2">฿200</div>
            </div>
            <div class="row">
              <div class="col-6 text-right mt-2">Discount</div>
              <div class="col-6 total-border mt-2">฿180</div>
            </div>
            <div class="row">
              <div class="col-6 text-right mt-2">Total</div>
              <div class="col-6 total-border mt-2">฿180</div>
            </div>
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
