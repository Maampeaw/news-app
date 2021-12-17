<template>
  <div>
    <div class='category'>{{ category }}</div>

  <div class='news-wrapper'>
    <div v-for="(news, id) in generalNews" :key="id" class='card'>
      <img class='img' :src="news.urlToImage" alt="" />
      <div class='title'>{{ news.title.slice(0, 52) }}...</div>
      <div class="description">{{news.description}}.... <strong>Read more</strong></div>
      <hr>
      <div class='author'>Author: <em>{{news.author}}</em></div>
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
