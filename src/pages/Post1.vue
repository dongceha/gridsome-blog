<template>
  <Layout>
      <div>
          <h1>Post1</h1>
          <ul>
              <li v-for="post in posts" :key="post.id">{{post.title}}</li>
          </ul>
      </div>
  </Layout>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            posts: []
        }
    },
    async created () {
        const { data } = await axios.get('https://jsonplaceholder.typicode.com/posts')
        this.posts = data
    }
}
</script>

<style>

</style>