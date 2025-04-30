<script>
import Nav from "./components/Nav.vue"

export default {
  components: {Nav},
  data() {
    return {
      pets: [
        { id: 1, name: "Buddy", type: "Dog", age: 2, adopted: false },
        { id: 2, name: "Mittens", type: "Cat", age: 3, adopted: true },
        { id: 3, name: "Polly", type: "Parrot", age: 1, adopted: false },
        { id: 4, name: "Charlie", type: "Dog", age: 4, adopted: true },
        { id: 5, name: "Whiskers", type: "Cat", age: 2, adopted: false },
      ],
      searchResult: ''
    }
  },
  methods: {
    handleSearch() {
      const pet = this.pets.find(pet => pet.name.toLowerCase() === name.toLowerCase())
      if (pet) {
        this.searchResult = `${pet.name} is ${pet.adopted ? "adopted" : "available"} `
      } else {
        this.searchResult = `Pet by the name of ${name} not found`
      }
    }
  }
}
</script>

<template>
  <div>
    <Nav @search-pet="handleSearch" />
    <p>{{ searchResult }}</p>
    <router-view :pets="pets" />
  </div>
</template>