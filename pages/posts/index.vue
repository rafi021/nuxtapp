<template>
  <div class="">
    <h2>Making API request - the nuxt way</h2>
    <div class="container">
      <div class="row">
        <div class="col-12 mb-2">
          <PostItemVue v-for="post in posts" :key="post.id" :post="post"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import PostItemVue from '~/components/PostItems.vue';
export default {
  components: {
    PostItemVue
  },
  data() {
    return {
      posts: '',
    }
  },
  async asyncData(context) {
    let { data } = await axios.get('https://jsonplaceholder.typicode.com/posts')
    return { posts: data }
  },

  head: {
    title: 'List of Posts',
  },
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
