<template>
  <div class="mt-5">
    <div class="container">
    <div>{{ this.cart }}</div>
      <table class="table table-hover table-responsive-md">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">Name</th>
            <th scope="col">Price</th>
            <th scope="col" class="text-center">Add to cart</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(book,key) in allbook" >
            <th scope="row">{{(key+1)}}</th>
            <td>
              <div class="row">
                <div class="col-md-2">
                  <img v-bind:src="book.cover" class="img-book" alt=""/>
                </div>
                <div class="col-md-4">{{book.title}}</div>
              </div>
            </td>
            <td>{{book.price}}</td>
            <td class="text-center"><button @click="addtocart" :value="book.id" class="btn btn-outline-dark">Add to Cart</button></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import books from '../books.json'

export default {
  name: 'Home',
  data () {
    return {
      allbook: books.books,
      incart : this.cart
    }
  },
  methods: {
    addtocart: function (e) {
      // console.log(e.target.value)
      this.allbook.forEach(element => {
        if(element.id==e.target.value){
          if(typeof element.count == 'undefined'){
            element.count=1;
          }else{
            element.count = (element.count) + 1;
          }
          this.cart[e.target.value]=element;
        }
      });
      console.log(this.cart)
    }
  },
  props: ['cart'],
  mounted () {
    if (this.cart) {
      this.incart = this.cart
    }
  }
}
</script>
