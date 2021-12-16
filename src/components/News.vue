<template>
  <div>
    <div class='category'>{{ category }}</div>

    <div class='news-wrapper'>
    <div v-for="(news, id) in generalNews.slice(0, 6)" :key="id" class='card'>
      <img class='img' :src="news.urlToImage" alt="" />
      <div class='title'>{{ news.title.slice(0, 52) }}........</div>
      <div>{{news.description.slice(0, 70)}}....<strong>Read more</strong></div>
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

<style >

.card{
  width: 200px;
 
}

.category{
  font-size: 16pt;
  padding-left: 70px;
  margin-bottom: 12px;
}
.news-wrapper{
  margin: auto;
  width: 90%;
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
}
.img{
  width: 200px;
}
.title{
  font-weight: bolder;
  text-transform: capitalize;
  margin: 5px 0;
}
@media screen and (max-width: 765px) {
  .news-wrapper{
    display: inline-grid;
    grid-template-columns: auto auto auto;
    grid-gap: 30px;
    padding: 10px;
  }
  .news-wrapper{
    width: 150px;
  }
  .img{
    width: 150px
  }
  .card{
    width: 150px;
  }
}

</style>
