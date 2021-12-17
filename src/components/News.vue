<template>
  <div>
    <div class='category'>{{ category }}</div>

    <div class='news-wrapper'>
    <div v-for="(news, id) in generalNews" :key="id" class='card'>
      <img class='img' :src="news.urlToImage" alt="" />
      <div class='title'>{{ news.title.slice(0, 52) }}........</div>
      <div>{{news.description.slice(0, 70)}}....<strong>Read more</strong></div>
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

<style >

.card{
  width: 300px;
  height: 350px;
  /* background: gray; */
 
}

.category{
  font-size: 16pt;
  padding-left: 70px;
  margin-bottom: 12px;
}
.news-wrapper{
  margin: auto;
  width: 90%;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  
}
.img{
  width: 100%;
  height: 180px;
}
.title{
  font-weight: bolder;
  text-transform: capitalize;
  margin: 5px 0;
}
.author{
  margin-top: 8px;
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
