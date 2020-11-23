<template>
    <div id="view-blog">
        <button @click="viewBlog()">view blog</button>
        <div class ="blog-container" v-for="content in contents" :key="content[0]">
        <h2>{{ content[2] }}</h2>
        <p>{{ content[3] }}</p>
        
    
        <update-blog :id="content[0]"></update-blog>
        <delete-blog :id="content[0]"></delete-blog>
    </div>
    </div>
</template>

<script>
import axios from "axios"
import UpdateBlog from "./UpdateBlog.vue"
import DeleteBlog from "./DeleteBlog.vue"
    export default {
        data() {
            return {
                 username: "",
                 contents: "",
                 created_at: [],
                 id: "",
            }
        },
        components: {
            UpdateBlog,
            DeleteBlog,
        },

        methods: {
            viewBlog: function() {
               axios.request({
                   url: "https://biggleblog.ga/api/blog_post",
                   method: "GET"
               }).then((response) =>{
                   console.log(response);
                   this.contents = response.data
               }).catch((error) => {
                   console.log(error);
               });
            },
        },
    }
</script>

<style  scoped>
#view-blog {
   margin: 0;
   padding: 20%;
   text-align:center;

}
.blog-container {
    padding: 6em;
}




</style>