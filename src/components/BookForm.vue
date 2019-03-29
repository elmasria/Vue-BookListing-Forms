<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <button type="submit" name="button">Add Book</button>

    <div class="">
      <label for="finishedReading">Finished Reading</label>
      <input type="checkbox" name="finishedReading" v-model="bookData.finishedReading">
      <label for="borrowed">borrowed</label>
      <input type="radio" name="borrowed" value="borrowed" v-model="bookData.ownership">

      <label for="bought">bought</label>
      <input type="radio" name="bought" value="bought" v-model="bookData.ownership">
    </div>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    }
  }
};
</script>

<style>
</style>
