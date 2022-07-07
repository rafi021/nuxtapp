<template>
<div class="">
  <h2>Making API request - the nuxt way</h2>
  <div class="container">
    <div class="row">
      <div class="col-12 mb-2" v-for="post in posts" :key="post.id">
        <div class="card">
          <div class="card-body">
            <h2 class="card-title">{{ post.title }}</h2>
            <p class="card-text">{{ post.body }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
import axios from 'axios';
export default{
  data(){
    return {
      posts: ''
    }
  },
  async asyncData(context){
    let response = await axios.get('https://jsonplaceholder.typicode.com/posts');
    return { posts: response.data }
  }
}
</script>


<!-- <script>
import axios from 'axios';

export default{
  data() {
    return{
      posts: []
    }
  },

  mounted() {
    axios.get('https://jsonplaceholder.typicode.com/posts')
    .then(response => {
      console.log(response.data);
      this.posts = response.data
    })
    .catch((error) => {
      console.log(error)
    })
  },


  methods: {

  }
}

</script> -->
