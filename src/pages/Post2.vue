<template>
  <Layout>
      <h1>Post2</h1>
      <ul>
            <li v-for="item in $page.posts.edges" :key="item.node.id">
                <g-link :to="`/posts/${item.node.id}`">
                    {{item.node.title}}
                </g-link>
            </li>
      </ul>
  </Layout>
</template>
<page-query>
query {
    posts: allPost {
        edges {
            node {
                id
                title
            }
        }
    }
}
</page-query>
<script>
export default {
    name: 'Psot'
}
</script>

<style>

</style>