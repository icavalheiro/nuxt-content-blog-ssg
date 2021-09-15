<template>
  <div id="wrapper">
    <!-- Header -->
    <Header />

    <!-- Main -->
    <div id="main">
      <div class="inner">
        <Nuxt />
      </div>
    </div>

    <!-- Footer -->
    <Footer />
  </div>
</template>

<script>
import Footer from "../components/Footer.vue";
import Header from "../components/Header.vue";

export default {
  components: {
    Footer,
    Header,
  },
};
</script>

