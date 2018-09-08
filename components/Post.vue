<template>
  <div class="post">
    <h1 class="title">{{ post.title }}</h1>
    <p>{{ post.body }}</p>
  </div>
</template>

<script>
  export default {
    props: {
      post: Object
    }
  }
</script>

<style>
  .post {
    margin-bottom: 30px;
  }
</style>

