<template>
  <div class="card">

    <p class="book-title">{{book.title}}</p>

    <img v-if="book.isbn" v-bind:src="'http://covers.openlibrary.org/b/isbn/' + book.isbn + '-M.jpg'" />

    <p class="book-author">{{book.author}}</p>
    
    <button v-on:click="toggleRead()" v-bind:class="{'mark-unread': book.read, 'mark-read': !book.read}">{{book.read?"Mark Unread":"Mark Read"}}</button>
    
  </div>
</template>

<script>
export default {
    name: 'book-card',
    props:['book'],
    methods: {
        toggleRead() {
            this.$store.commit("FLIP_READ_BUTTON",this.book)
            
        }
    }
}
</script>

<style>
.card {
    border: 2px solid black;
    border-radius: 10px;
    width: 250px;
    height: 550px;
    margin: 20px;
}

.card.read {
    background-color: lightgray;
}

.card .book-title {
    font-size: 1.5rem;
}

.card .book-author {
    font-size: 1rem;
}
</style>