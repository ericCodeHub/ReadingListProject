<template>
  <div>
      <form class="new-book-form" v-on:submit.prevent="addNewBook">
          <div>
            <label for="title">Title: </label>
            <input type="text" name="title" id="title" class="title-input" v-model="newBook.title" />
          </div>

          <div>
            <label for="author">Author: </label>
            <input type="text" name="author" id="author" class="author-input" v-model="newBook.author" />
          </div>

          <div>
          <label for="isbn">ISBN: </label>
          <input type="text" name="isbn" id="isbn" class="isbn-input" v-model="newBook.isbn" />
          </div>

          <div>
          <input type="submit" value="Add" />
          </div>          
      </form>
  </div>
</template>

<script>
export default {
    name: "new-book-form",
    data() {
        return {
            newBook: {
                read: false,
            },
        }; 
    },   
    methods: {
        addNewBook() {
            this.$store.commit("ADD_BOOK",this.newBook);
            this.resetForm();
        },
        resetForm() {
            this.newBook = {};
        }

    },
}
</script>

<style>

</style>