<template>
    <div>
        <p>enter username</p>
         <input v-model="username" type="text" />
         <textarea v-model="content"></textarea>
         <button @click="updateBlog()">update</button>
    
    </div>
</template>

<script>
import axios from "axios"
    export default {
        name: "UpdateBlog",
        data() {
            return {
                username: "",
                content: "",
                id:"",
               
           
            };
        },
        props: {
            id: {
                type: Number,
                default: 0,
            },
        },
        methods: {
            updateBlog: function() {
                axios.request({
                    url: "https://bigblog.gq/api/blog_post",
                    method: "PATCH",
                    headers: {
                         "Content-Type": "application/json",
                    },
                    data: {
                        username: this.username,
                        content: this.content,
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