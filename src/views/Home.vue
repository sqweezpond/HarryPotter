<template>
  <div class="mt-5">
    <div class="container">
    <div>{{ msg }}</div>
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
          <tr v-for="(home,key) in valuebook" v-bind:key="key">
            <th scope="row">{{(key+1)}}</th>
            <td>
              <div class="row">
                <div class="col-md-2">
                  <img v-bind:src="home.cover" class="img-book" alt=""/>
                </div>
                <div class="col-md-4">{{home.title}}</div>
              </div>
            </td>
            <td>{{home.price}}฿</td>
            <td class="text-center">
              <button @click="pushBooks" :value="home.id" class="btn btn-outline-dark">Add <i class="fas fa-plus-circle ml-1"></i></button>
            </td>
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
      valuebook: books.books,
      welcome: 'This is your profile'
    }
  },
  methods: {
    pushBooks: function (e) {
      this.msg.push(e.target.value)
    }
  },
  props: ['msg'],
  mounted () {
    if (this.msg) {
      this.welcome = this.msg    
    }
  }
}
</script>
