<template>
  <section class="comment-form">
    <h3>{{formTitle}}</h3>
    <div>
      <input placeholder="author" v-model="author">
      <input placeholder="content" v-model="body">
      <button v-on:click="addComment">保存</button>
    </div>
  </section>
</template>

<script>
 export default {
   props: ["formTitle"],
   data: function () {
     return {
       author: "",
       body: ""
     };
   },
   methods: {
     addComment: function() {
       this.$emit("add-comment", {
         author: this.author,
         body: this.body
       });
       this.author = this.body = "";
     }
   }
 };
</script>

<style scoped>
 .comment-form {
   width: 400px;
   margin: 0 auto;
 }
 .comment-form > div {
   display: flex;
   flex-flow: column;
 }
 input {
   margin-bottom: 1em;
   padding: 10px;
 }
 button {
   padding: 10px;
   border: 0;
 }
</style>