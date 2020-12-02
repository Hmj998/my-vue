<template>
  <section class="comment-list">
    <h3>{{title}}</h3>
    <div class="comment" v-for="c in comments" :key="c.id">
      <span class="author">{{c.author}}</span>
      <span class="body">{{c.body}}</span>
      <a href="#" class="del" v-on:click="delComment(c.id)">删除</a>
    </div>
  </section>
</template>

<script>
 export default {
   props: ["title", "comments"],
   data: function () {
     return {
     }
   },
   methods: {
     delComment(id){
       this.$emit("delete-comment", id);
     }
   }
 };
</script>

<style scoped>
 .comment-list {
   width: 400px;
   margin: 2em auto;
 }
 .comment {
   border: 1px solid #eee;
   padding: 1em;
   margin-bottom: 1em;
   display: flex;
 }
 .author {
   flex: 0 0 50px;
 }
 .body {
   flex: 1;
 }
 .del {
   flex: 0 0 50px;
 }
</style>