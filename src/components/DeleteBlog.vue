<template>
    <div>
        <button @click="DeleteBlog()">Delete</button>
  
    </div>
</template>

<script>
import axios from "axios";
    export default {
       name: "DeleteBlog",
       
       props: {
           id: {
               type: Number,
               default: 0, 
           },
       },
       methods: {
           DeleteBlog: function() {
               axios.request({
                   url: "http://127.0.0.1:5000/blog_post",
              method: "DELETE",
              headers: {
                  "Content-Type": "application/json",
              },
              data: {
                  id: this.id,
              }
               }).then((response) => {
                   console.log(response)
               }).catch((error) => {
                   console.log(error)
               })
           }
       },
    };
</script>

<style scoped>

</style>