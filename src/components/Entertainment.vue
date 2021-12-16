<template>
  <div>
    <div class='category'>{{ category }}</div>

  <div class='news-wrapper'>
    <div v-for="(news, id) in generalNews" :key="id" class='card'>
      <img width="200" :src="news.urlToImage" alt="" />
      <p>{{ news.title }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
export default {
  mounted() {
    this.fetchNews(this.category);
  },
  name: "News",
  computed: {
    category() {
      return this.$route.params.name ? this.$route.params.name : "general";
    },
    ...mapGetters(["generalNews"]),
  },
  methods: {
    getNews() {
      this.fetchNews(this.category);
    },
    ...mapActions(["fetchNews"]),
  },
};
</script>

<style></style>
