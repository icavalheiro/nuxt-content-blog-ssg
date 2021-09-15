<template>
  <header id="header">
    <div class="inner">
      <!-- Logo -->
      <a href="/E" class="logo">
        <span class="symbol">
          <img src="/images/logo.svg" alt="" />
        </span>
        <span class="title">{{ config.blog_name || "" }}</span>
      </a>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      config: {},
    };
  },
  async fetch() {
    this.config = await this.$content("config").fetch();
  },
};
</script>
