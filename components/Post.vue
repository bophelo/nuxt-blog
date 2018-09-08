<template>
  <div class="post">
    <h1 class="post__title">
      <nuxt-link :to="{name: 'posts-id', params: { id: post.id } }">{{ post.title }}</nuxt-link>
    </h1>
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

<style lang="scss">
  .post {
    margin-bottom: 40px;

    &__title {
      font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
      display: block;
      font-weight: 300;
      color: #35495e;
    }
  }
</style>

