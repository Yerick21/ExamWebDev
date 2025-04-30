<script>
import { RouterLink, RouterView } from 'vue-router'
import Nav from './components/Nav.vue'

import 'bootstrap/dist/css/bootstrap.min.css'
import 'bootstrap/dist/js/bootstrap.bundle.min.js'


export default {
  components: {Nav},

  data() {
    return {
      pets: [
        {id: 1, name: 'Hermes', type : 'Dog', age: 2, adopted:true},
        {id: 2, name: 'Chewie', type : 'Cat', age: 4, adopted:false},
        {id: 3, name: 'Redwing', type : 'Bird', age: 1, adopted:true},
        {id: 4, name: 'Krypto', type : 'Dog', age: 5, adopted:false},
        {id: 5, name: 'Bats', type : 'Dog', age: 2, adopted:false},
      ],
      searchResults: ''
    }
  },

  methods: {
    handleSearch(name){
      const pet = this.pets.find(pet => pet.name.toLowerCase() === name.toLowerCase());
      if (pet) {
        this.searchResults = `${pet.name} is ${pet.adopted ? 'adopted' : 'available'}`;
      }
      else {
        this.searchResults = `no pet not found by the name ${name}`;
      }
    }
  }
}
</script>

<template>
  <div>
    <Nav @search-pet="handleSearch" />
    <p> {{ searchResults }} </p>
    <RouterView  :pets="pets" />
  </div>

  
</template>

<style>

</style>
