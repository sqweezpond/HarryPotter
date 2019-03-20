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
            <th scope="col" class="text-center">Add</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(list,key) in valuebook" v-bind:key="key">
            <th scope="row">{{(key+1)}}</th>
            <td>
              <div class="row">
                <div class="col-md-2">
                  <img v-bind:src="list.cover" class="img-book" alt=""/>
                </div>
                <div class="col-md-4">{{list.title}}</div>
              </div>
            </td>
            <td>{{list.price}}</td>
            <td class="text-center"><button @click="pushBooks" :value="list.id" class="btn btn-outline-dark">Add to Cart</button></td>
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
      //console.log(e.target.value)
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
