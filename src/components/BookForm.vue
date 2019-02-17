<template>
  <form class="" action="#" method="post" v-on:submit.prevent="bookSubmit(bookData)">
      <input type="text" name="title" v-model='bookData.bookTitle' value="" placeholder="Book Title">
      <input type="text" name="author" v-model='bookData.bookAuthor' value="" placeholder="Book Author">
      <div>
          <input type="checkbox" name="finishedReading" v-model='bookData.finishedReading'/>
          <label for="finishedReading">Finished Reading</label>
      </div>
      <input type="radio" name="borrowed" v-model='bookData.ownership' value="borrowed"><label for="borrowed">Borrowed</label>
      <input type="radio" name="bought" v-model='bookData.ownership' value="bought"><label for="bought">Bought</label>
      <button type="submit" name="button">Add Book</button>
  </form>
</template>
<script>
  export default{
    name : 'BookForm',
    props : 'books',
    data(){
      return {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: [],
      }
    },
    methods :{
      bookSubmit(bookData){
        this.$emit('addBook', bookData );
      }
    },
  }
</script>
<style>

</style>
