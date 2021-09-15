<template>
  <div>
    <header>
      <h1>
        {{ config.blog_title }}
      </h1>
      <p>
        {{ config.blog_subtitle }}
      </p>
    </header>
    <section class="tiles">
      <PostCTA v-for="(post, i) in posts" :key="i" :post="post" />
    </section>
  </div>
</template>

<script>
import PostCTA from "../components/PostCTA.vue";

export default {
  components: {
    PostCTA,
  },
  async asyncData({ $content }) {
    const posts = await $content("blog").fetch();
    const config = await $content("config").fetch();

    return { posts, config };
  },
};
</script>
