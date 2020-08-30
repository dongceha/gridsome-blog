<template>
<Layout>
  <!-- Page Header -->
  <header class="masthead" style="background-image: url('/img/home-bg.jpg')">
    <div class="overlay"></div>
    <div class="container">
      <div class="row">
        <div class="col-lg-8 col-md-10 mx-auto">
          <div class="site-heading">
            <h1># {{$page.tag.title}}</h1>
          </div>
        </div>
      </div>
    </div>
  </header>

  <!-- Main Content -->
  <div class="container">
    <div class="row">
      <div class="col-lg-8 col-md-10 mx-auto">
        <div class="post-preview" v-for="post in $page.tag.posts" :key="post.id">
          <g-link :to="`/posts/${post.id}`">
            <h2 class="post-title">
              {{post.title}}
            </h2>
          </g-link>
          <!-- <p class="post-meta">Posted by
            <a href="#">
              {{`${post.created_by.firstname} ${post.created_by.lastname}`}}
            </a>
            on 
            {{edge.node.created_at}}
          </p> -->
          <hr>
        </div>
      </div>
    </div>
  </div>
</Layout>
</template>
<page-query>
query($id: ID!) {
  tag: strapiTag (id: $id) {
    id
    title
    posts {
      title
      content
      created_by
    }
    created_by{
      lastname
      firstname
    }
    created_at
  }
}
</page-query>
<script>

export default {
    name: 'TagPage'
}
</script>

<style>

</style>