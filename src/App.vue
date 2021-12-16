<template>
  <div id="app">
    <Navbar />

  <div class="date">{{date.toDateString()}}</div>

    <div class="main"><router-view /></div>

    <Footer />
  </div>
</template>
<script>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue"
export default {
  name: "App",
  data(){
    return{
      date: new Date()
    }
  },
  components: { Navbar, Footer },
};
</script>

<style>
#app {
  background-color: #7640F6;
  color:white;
}
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.date{
  margin: 16px 0;
  padding-left: 70px;
  font-size: 16pt;
  
}


/* .main{
  font-size: 32px;
} */
</style>
