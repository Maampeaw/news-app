<template>
  <div class="nav">

    <div class="logo"><img src="../assets/logo.png" alt=""></div>
    <div class="hanburger"><img src="../assets/menu.png" alt=""></div>
    <div class='links'>
    <router-link :to="{ name: 'General', params: { name: 'general' } }"
      >General</router-link
    >
    <router-link :to="{ name: 'Tech', params: { name: 'technology' } }"
      >Technology</router-link
    >
    <router-link :to="{ name: 'Sports', params: { name: 'sports' } }"
      >Sports</router-link
    >
    <router-link
      :to="{ name: 'Entertainment', params: { name: 'entertainment' } }"
      >Entertainment</router-link
    >
  </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style scoped>
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 50px;
  align-items: center;
  padding: 70px;
  box-shadow: 0px 4px 4px rgba(255, 255, 255, 0.25);
}
.links{
  display: flex;
  gap: 30px;

}
.links a{
  text-decoration: none;
  color: white;
  font-family: sans-serif;
}
.hanburger{
  display: none;
}
@media screen and (max-width:765px) {
    .links{
    display: none;
}
.hanburger{
  display: block;
}
}
</style>
