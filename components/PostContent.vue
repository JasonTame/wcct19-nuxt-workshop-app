<template>
  <div class="max-w-md leading-loose tracking-tight">
    <h1 class="font-bold my-12" v-html="currentPost.title.rendered"></h1>
    <div class="post-content" v-html="currentPost.content.rendered"></div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: this.currentPost.title.rendered
    };
  },
  computed: {
    currentPost() {
      let postSlug = this.$route.params.slug
        ? this.$route.params.slug
        : this.$store.state.posts[0].slug;

      let currentPost = this.$store.state.posts.find(
        post => post.slug == postSlug
      );

      this.$store.commit("setCurrentPost", currentPost);
      return currentPost;
    }
  }
};
</script>