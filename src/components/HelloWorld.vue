<template>
<div>
  <div class="post" v-for="post in posts" :key="post.id">
     <h3>Title: {{ post.title}} </h3>
     <P>Description:{{ post.body}}</p>
  </div>
  </div>
</template>
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
<script>
import axios from 'axios';
export default {
  data () {
    return {
      posts: []
    }
  },
  mounted()
  {var self = this;
     axios.get('https://jsonplaceholder.typicode.com/posts')
      .then(function(res){
       self.posts = res.data;
       console.log('Data:',res.data);
      })
     .catch(function(error){
       console.log('Error:',error);
      } )
  }
}
</script>
