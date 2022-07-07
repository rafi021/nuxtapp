<template>
<div class="">
  <h2 class="card-title">{{ post.title }}</h2>
  <p class="card-text">{{ post.body }}</p>

  <nuxt-link class="" to="/posts">Back to posts</nuxt-link>
</div>
</template>

<script>
import axios from 'axios'

export default{
  data() {
    return{
      post:''
    }
  },
  async asyncData(context){
    let {data} = await axios.get(`https://jsonplaceholder.typicode.com/posts/${context.params.id}`)

    return { post: data }
  },
  head(){
    return{
      title: this.post.title
    }
  }
}
</script>
