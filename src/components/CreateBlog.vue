<template>
    <div id="create-blog">
        <p>enter username</p>
         <input v-model="username" type="text" />
         <p>enter yyyy-dd-mm</p>
         <input v-model="created_at" type="text" />
         <p>MAKE A POST</p>
         <textarea v-model="content"></textarea>
         <p>create a post</p>
         <button @click="createBlog">Submit</button>
         
         
    
    </div>
</template>

<script>
import axios from "axios"
    export default {
        data() {
            return {
               username: "",
               content: "",
               created_at: "",
            }
        },
        methods: {
            createBlog: function() {
                axios.request({
                    url:"http://127.0.0.1:5000/blog_post",
                    method: "POST",
                    headers:{
                        "Content-Type": "application/json"
                    },
                    data: {
                        username: this.username,
                        content: this.content,
                       
                        created_at: this.created_at,

                    }
                }).then((response) => {
                    console.log(response)
                }).catch((error) => {
                    console.log(error)
                })
            }
        },
    }
</script>

<style scoped>
#create-blog {

   margin: 0;
   padding: 20%;
   text-align:center;


}


</style>