<template>
  <div class="book-container">    
      <book-card  v-for="book in $store.state.books" v-bind:key="book.isbn" v-bind:book="book" v-bind:class="{read: book.read}" />

    
    
  
  </div>
</template>

<script>
import BookCard from './BookCard.vue'

export default {
  components: { BookCard },
    name: 'reading-list'
    
}
</script>

<style>
.book-container {
    display:flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
  
    
}
.card {
  border: 1px black solid;
  border-radius: 6px;
  padding: 1rem;
  margin: 10px;
  width: 15%;
  height: 500px;
}

</style>