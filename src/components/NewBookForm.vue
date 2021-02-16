<template>
  <div class="new-book-form">
      <form  v-on:submit.prevent="addNewBook">
          <div class = "form-item">
            <label for="title">Title: </label>
            <input type="text" name="title" id="title" class="title-input" v-model="newBook.title" />
          </div>

          <div class = "form-item">
            <label for="author">Author: </label>
            <input type="text" name="author" id="author" class="author-input" v-model="newBook.author" />
          </div>

          <div class = "form-item">
          <label for="isbn">ISBN: </label>
          <input type="text" name="isbn" id="isbn" class="isbn-input" v-model="newBook.isbn" />
          </div>

          <div class = "form-item">
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
.new-book-form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    max-width: 10%;
    margin: 0 auto;
    
}
.form-item {
    display: flex;
    justify-content: flex-end;
    padding: 5px;
    
}
.form-item label{
    padding: 5px;
}
.form-item input{
    padding: 5px;
}
</style>