<template>
  <div class="grid-container">
  <div id="app">
     <p style="text-decoration: underline">BIG BLOG!</p>
   <view-blog></view-blog>
   <create-blog></create-blog>
  </div>
  </div>
</template>

<script>
import ViewBlog from './components/ViewBlog.vue'
import CreateBlog from './components/CreateBlog.vue'





export default {
  name: 'App',
  components: {
    ViewBlog,
    CreateBlog,
    
    
    
  }
}
</script>

<style scoped>


.grid-container {
   grid-template-rows: minmax(250px, 1fr);
   text-align:center;
}
style {
  font-family: 'Oswald', bold, sans-serif;
  font-size: 20px;
  
};

#app {
  
  font-family: 'Oswald', bold, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: red;
  margin-top: 60px;
}

</style>
