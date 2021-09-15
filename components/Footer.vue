<template>
  <footer id="footer">
    <div class="inner" v-if="config">
      <section>
        <h2>Follow</h2>
        <ul class="icons">
          <li v-for="(socialMedia, i) in config.social_medias" :key="i">
            <NuxtLink
              :to="socialMedia.url"
              :class="'icon style2 ' + socialMedia.icon"
            >
              <span class="label">{{ socialMedia.label }}</span>
            </NuxtLink>
          </li>
        </ul>
      </section>
      <ul class="copyright">
        <li>{{ config.copyright }}</li>
        <li>{{ config.credits }}</li>
      </ul>
    </div>
  </footer>
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
