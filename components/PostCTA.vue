<template>
  <article :class="style">
    <span class="image">
      <img :src="post['header-image']" alt="" />
    </span>
    <NuxtLink :to="'/posts/' + post.slug">
      <h2>{{ post.title }}</h2>
      <div class="content">
        <p>
          {{ post.description }}
        </p>
      </div>
    </NuxtLink>
  </article>
</template>

<script>
let availableStyles = [
  "style1",
  "style2",
  "style3",
  "style4",
  "style5",
  "style6",
];

let currentStyle = 0;
export default {
  props: {
    post: Object,
  },
  data() {
    let style = availableStyles[currentStyle];
    currentStyle++;
    if (currentStyle >= availableStyles.length) currentStyle = 0;

    return {
      style,
    };
  },
};
</script>

<style scoped>
img {
  width: 353px;
  height: 326px;
}
</style>
