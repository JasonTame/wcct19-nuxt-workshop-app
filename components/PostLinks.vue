<template>
  <div>
    <ul class="flex flex-wrap justify-between flex-col">
      <li :key="post.id" v-for="post in posts">
        <nuxt-link :to="`/posts/${post.slug}`" v-html="post.title.rendered"></nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    posts: {}
  }
};
</script>

