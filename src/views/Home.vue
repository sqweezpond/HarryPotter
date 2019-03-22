<template>
  <div class="container mt-5">
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
            <td class="text-center"><button @click="addtocart" :value="book.id" class="btn btn-outline-dark">Add <i class="fas fa-plus-circle ml-2"></i></button></td>
          </tr>
        </tbody>
      </table>
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
      incart: this.cart
    }
  },
  methods: {
    addtocart: function (e) {
      this.allbook.forEach(element => {
        // cc = (cc + element.count)
        if(element.id==e.target.value){
          if(typeof element.count == 'undefined'){
            element.count=1
          }else{
            element.count = (element.count) + 1
          }
          this.cart[e.target.value]=element
        }
      })

      var cc = parseInt(this.cartcount)
      var obj = this.cart
      for (var key in obj) {
        cc = (cc + parseInt(obj[key].count))
      }
      console.log(cc)
      // this.cartcount = cc
    },
  },
  props: ['cart','cartcount'],
  mounted () {
    if (this.cart) {
      this.incart = this.cart
    }
  }
}
</script>
