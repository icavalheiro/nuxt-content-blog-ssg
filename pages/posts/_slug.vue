<template>
  <div>
    <div class="blog-head">
      <h1>{{ post.title }}</h1>
    </div>
    <nuxt-content :document="post" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    try {
      const post = await $content("blog/" + params.slug).fetch();
      return { post };
    } catch (e) {
      error({ statusCode: 404, message: e });
    }
  },
};
</script>
